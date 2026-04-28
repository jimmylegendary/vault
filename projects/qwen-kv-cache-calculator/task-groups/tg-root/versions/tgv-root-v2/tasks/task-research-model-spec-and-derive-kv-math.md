---
taskOpsVersion: v1
entityType: task
id: task-research-model-spec-and-derive-kv-math
taskGroupId: tg-root
taskGroupVersionId: tgv-root-v2
title: 모델 스펙 확인 및 KV cache 계산식 도출
objective: Qwen3.5-27B의 실제 config를 확인하고 1M token, batch 1 기준 KV cache 계산식을 근거와 함께 도출한다.
responsibility: 모델 아키텍처 확인과 수식 정리
completionCriteria: 사용한 스펙 값과 수식, 단위 변환, A100 관점 해석까지 문서로 명확히 정리된다.
order: 1
createdAt: 2026-04-28T03:09:14.120Z
status: done
---
# 모델 스펙 확인 및 KV cache 계산식 도출

- Outcome doc: `derived/views/qwen35-27b-kv-cache-derivation.md`
- Qwen3.5-27B config 기준으로 1M token / batch 1 KV cache를 65.536 GB (= 61.04 GiB)로 도출했다.
