# Qwen3.5-27B serving topology notes

## What TP changes
Tensor Parallel (TP) splits attention heads / projection weights across ranks.
For the calculator, the main practical approximation is:

- global KV cache stays the same for the request
- **per-GPU KV cache ≈ global-or-replica KV / TP**
- **per-GPU dense weight memory ≈ total weight memory / TP**

## What DP changes
Data Parallel (DP) does **not** make one request cheaper on one replica.
Instead it increases the number of independent replicas that can serve requests.

So in the calculator:
- DP does not reduce per-replica weight shard size
- DP can reduce per-replica KV only if you assume the global batch is split across replicas
- DP increases total cluster footprint because each replica needs its own copy of the sharded weights

## What EP changes here
For Qwen3.5-27B specifically, EP is effectively a no-op in this calculator because this model is dense.
There is no expert-only shard pool to redistribute like a routed MoE model.

That is why the page exposes EP as a target-system toggle / planning note, but does not change the dense 27B memory result yet.

## Important caution
These numbers are planning estimates, not a runtime profiler.
Real serving also needs room for:
- activations
- allocator fragmentation
- scheduler/runtime buffers
- graph capture/workspace overhead
- non-attention state in hybrid layers

So even when the page says a setup "fits", that should be read as:
- **might fit in principle**
- not **guaranteed production safe without headroom testing**
