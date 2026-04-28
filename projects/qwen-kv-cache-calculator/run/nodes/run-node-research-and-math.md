---
taskOpsVersion: v1
entityType: runNode
id: run-node-research-and-math
runId: run-main
type: research
title: Qwen3.5-27B 스펙 확인 및 KV cache 계산 도출
objective: 실제 config를 확인하고 1M token / batch 1 KV cache를 계산한다
status: done
sourceTaskId: task-research-model-spec-and-derive-kv-math
sourceTaskGroupVersionId: tgv-root-v2
createdAt: 2026-04-28T03:15:00.000Z
---
# Qwen3.5-27B 스펙 확인 및 KV cache 계산 도출

- Hugging Face config를 확인했다.
- full-attention 16 layers 기준 KV cache를 61.04 GiB로 계산했다.
