---
taskOpsVersion: v1
entityType: runNode
id: run-node-playtest-deploy-blocker
runId: run-main
type: planning
title: playtest build 배포 타깃 결정 대기
objective: 외부에 공유 가능한 build를 올리기 전에 visibility와 deploy target 결정을 받는다
status: blocked
sourceTaskId: task-ship-shareable-playtest-build
sourceTaskGroupVersionId: tgv-root-v4
createdAt: 2026-04-27T19:18:00.000Z
---
# playtest build 배포 타깃 결정 대기

- public/private access policy와 deploy target 결정이 필요하다.
- 추천 선택지를 사용자에게 질의한다.
