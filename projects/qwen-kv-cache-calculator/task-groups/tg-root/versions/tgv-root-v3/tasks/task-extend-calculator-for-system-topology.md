---
taskOpsVersion: v1
entityType: task
id: task-extend-calculator-for-system-topology
taskGroupId: tg-root
taskGroupVersionId: tgv-root-v3
title: TP/DP/EP 및 serving topology 확장
objective: 계산기에 target system 구성과 serving param을 넣어 per-GPU / per-replica / cluster 관점 메모리 추정을 볼 수 있게 한다.
responsibility: 시스템 토폴로지와 serving 가정 모델링
completionCriteria: TP, DP, EP 여부/크기, GPU 메모리, utilization, replica 관점 결과를 조절하며 즉시 계산할 수 있다.
order: 1
createdAt: 2026-04-28T03:22:12.469Z
status: done
---
# TP/DP/EP 및 serving topology 확장

- Extended the calculator with TP/DP/EP-aware target-system controls and serving assumptions.
- Outcome docs: `derived/views/qwen35-27b-kv-cache-derivation.md`, `derived/views/qwen35-27b-serving-topology-notes.md`
- Local browser recalculation verified.
