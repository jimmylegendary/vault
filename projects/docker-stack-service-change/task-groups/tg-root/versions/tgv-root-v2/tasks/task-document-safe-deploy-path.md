---
taskOpsVersion: v1
entityType: task
id: task-document-safe-deploy-path
taskGroupId: tg-root
taskGroupVersionId: tgv-root-v2
title: A/C 무중단 기준 안전한 deploy 경로 문서화
objective: stack deploy에서 D 추가와 B 제거를 어떤 옵션 조합으로 처리할지 명확히 정리한다.
responsibility: 명령 경로와 운영 주의사항 정리
completionCriteria: non-prune / prune 차이와 검증 절차가 문서로 정리된다.
order: 1
createdAt: 2026-04-28T08:32:34.077Z
status: done
---
# A/C 무중단 기준 안전한 deploy 경로 문서화

- Outcome doc: `derived/views/docker-stack-add-service-runbook.md`
- `stack deploy` vs `stack deploy --prune` 차이와 추천 운영 순서를 정리했다.
