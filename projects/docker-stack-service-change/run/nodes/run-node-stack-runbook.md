---
taskOpsVersion: v1
entityType: runNode
id: run-node-stack-runbook
runId: run-main
type: documentation
title: Docker stack D 추가 / B 제거 runbook 작성
objective: stack deploy에서 prune 유무에 따라 어떤 동작이 나는지 명확히 설명한다
status: done
sourceTaskId: task-document-safe-deploy-path
sourceTaskGroupVersionId: tgv-root-v2
createdAt: 2026-04-28T08:38:00.000Z
---
# Docker stack D 추가 / B 제거 runbook 작성

- `docker stack deploy`와 `docker stack deploy --prune`의 차이를 정리했다.
- A/C 무중단 조건과 추천 운영 순서를 문서화했다.
