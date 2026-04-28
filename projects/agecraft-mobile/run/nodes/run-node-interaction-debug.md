---
taskOpsVersion: v1
entityType: runNode
id: run-node-interaction-debug
runId: run-main
type: implementation
title: 모바일 interaction blocker 디버깅
objective: 모바일/웹뷰에서 버튼 입력이 먹지 않는 문제를 재현하고 수정한다
status: done
sourceTaskId: task-fix-mobile-interaction-blocker
sourceTaskGroupVersionId: tgv-root-v6
createdAt: 2026-04-28T02:30:00.000Z
---
# 모바일 interaction blocker 디버깅

- decorative canvas의 pointer-events를 차단했다.
- overlay z-index/pointer-events와 button touch-action을 명시했다.
- local Playwright harness로 gather/select/craft/reset click path를 확인했다.
