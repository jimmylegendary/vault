---
taskOpsVersion: v1
entityType: runNode
id: run-node-topology-redeploy
runId: run-main
type: implementation
title: topology 확장 계산기 재배포 확인
objective: topology-aware calculator를 live로 재배포하고 sanity check를 통과시킨다
status: done
sourceTaskId: task-reverify-and-redeploy-extended-calculator
sourceTaskGroupVersionId: tgv-root-v3
createdAt: 2026-04-28T03:35:00.000Z
---
# topology 확장 계산기 재배포 확인

- app repo push 후 Vercel redeploy를 완료했다.
- local/live Playwright check로 TP/DP/EP-aware recalculation을 확인했다.
