---
taskOpsVersion: v1
entityType: runNode
id: run-node-fun-pacing-pass
runId: run-main
type: implementation
title: 핵심 재미 루프와 pacing pass 진행
objective: gather/craft/market bottleneck 리듬을 플레이테스트 친화적으로 조정한다
status: done
sourceTaskId: task-tune-core-fun-and-pacing
sourceTaskGroupVersionId: tgv-root-v4
createdAt: 2026-04-27T18:56:30.000Z
---
# 핵심 재미 루프와 pacing pass 진행

- focused gathering, faster shell drip, bottleneck-aware crafting bonuses를 추가했다.
- smoke path pacing을 23/46/51 gathers -> 18/41/41 gathers로 줄였다.
- `npm run smoke`와 `npm run build`를 통과했다.
