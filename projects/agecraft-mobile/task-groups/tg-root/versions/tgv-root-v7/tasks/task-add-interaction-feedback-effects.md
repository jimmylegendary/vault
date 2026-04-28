---
taskOpsVersion: v1
entityType: task
id: task-add-interaction-feedback-effects
taskGroupId: tg-root
taskGroupVersionId: tgv-root-v7
title: interaction feedback 효과 추가
objective: 버튼/선택/제작/구매 입력 시 사용자가 즉시 눌렸다는 확신을 느끼도록 시각적/촉각적 피드백을 강화한다.
responsibility: 입력 반응 UX 강화
completionCriteria: 핵심 interaction마다 즉시 보이는 반응 효과가 생기고 실제 플레이에서 입력 인지가 쉬워진다.
order: 1
createdAt: 2026-04-28T02:56:05.271Z
status: done
---
# interaction feedback 효과 추가

- 버튼 누름 반응, 짧은 토스트, 모바일 진동 힌트를 추가했다.
- local Playwright로 immediate feedback 동작을 확인했다.
- `npm run smoke`와 `npm run build`를 통과했다.
