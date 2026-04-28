# Qwen3.5-27B KV cache derivation

## Source model spec used
Primary source:
- Hugging Face config: `https://huggingface.co/Qwen/Qwen3.5-27B/raw/main/config.json`

Relevant `text_config` values:
- `num_hidden_layers = 64`
- `full_attention_interval = 4`
- `num_key_value_heads = 4`
- `head_dim = 256`
- `dtype = bfloat16`
- `max_position_embeddings = 262144`

Important architectural note:
- This model is hybrid.
- Only every 4th layer is `full_attention`.
- The other layers are `linear_attention` / recurrent-style layers and do **not** create the same O(sequence_length) KV cache growth as standard full attention.

So the full-attention layer count is:

`64 / 4 = 16 layers`

## KV cache formula
For standard attention KV cache:

`KV bytes = batch_size × sequence_length × num_full_attention_layers × num_kv_heads × head_dim × 2 (K and V) × bytes_per_value`

For Qwen3.5-27B in BF16:
- `batch_size = 1`
- `sequence_length = 1,000,000`
- `num_full_attention_layers = 16`
- `num_kv_heads = 4`
- `head_dim = 256`
- `2` for K and V
- `bytes_per_value = 2` for BF16

Substitute:

`KV bytes = 1 × 1,000,000 × 16 × 4 × 256 × 2 × 2`

Step by step:
- `4 × 256 = 1,024`
- `1,024 × 2 = 2,048`
- `2,048 × 2 = 4,096`
- `4,096 × 16 = 65,536`

So per token:

`65,536 bytes/token = 64 KiB/token`

For 1,000,000 tokens:

`65,536 × 1,000,000 = 65,536,000,000 bytes`

## Unit conversion
### Decimal GB
`65,536,000,000 / 1,000,000,000 = 65.536 GB`

### Binary GiB
`65,536,000,000 / 1,073,741,824 = 61.04 GiB`

## Result
### Qwen3.5-27B, batch 1, sequence 1,000,000, BF16 KV cache
- **65.536 GB**
- **61.04 GiB**

## A100 interpretation
### A100 40GB
- impossible from KV cache alone
- `61.04 GiB > 40 GB-class capacity`

### A100 80GB
- KV cache alone is theoretically within 80GB-class memory
- but it leaves only about `18.96 GiB` of headroom if you think in GiB terms against an 80 GiB card
- that is not enough for the full model weights in BF16

### Weight reality check
Very rough weight memory only:
- `27B params × 2 bytes ≈ 54 GB` (about `50.3 GiB`) just for BF16 weights

So on a **single A100 80GB**, `BF16 weights + 1M-token BF16 KV cache` is not realistic.

## Useful comparison: naive full-attention assumption
If someone incorrectly assumes all 64 layers use standard full attention, the KV cache would be 4x larger:

`1 × 1,000,000 × 64 × 4 × 256 × 2 × 2 = 262,144,000,000 bytes`

That equals:
- `262.144 GB`
- `244.14 GiB`

This is why the hybrid architecture matters a lot.

## Scope note
This derivation is for the **token-length-scaling attention KV cache**.
The linear/recurrent layers have additional state, but that state is not the dominant O(sequence_length) KV growth term and is negligible relative to the 61 GiB figure at 1M tokens.
