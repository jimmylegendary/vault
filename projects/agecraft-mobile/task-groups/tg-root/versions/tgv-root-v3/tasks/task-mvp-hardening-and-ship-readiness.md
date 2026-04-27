---
taskOpsVersion: v1
entityType: task
id: task-mvp-hardening-and-ship-readiness
taskGroupId: tg-root
taskGroupVersionId: tgv-root-v3
title: MVP 검증, 하드닝, 출시 준비
objective: 플레이어가 처음부터 다음 시대로 넘어가는 전체 루프를 무리 없이 경험하도록 다듬고 배포 가능한 상태로 만든다.
responsibility: QA, tuning, packaging, ship checklist 완료
completionCriteria: 새 플레이어 기준 end-to-end 루프가 끊기지 않고 실행되며 실행/배포 방법이 문서화된다.
order: 4
createdAt: 2026-04-27T18:17:24.679Z
status: done
---
# MVP 검증, 하드닝, 출시 준비

- Added deterministic reducer-level smoke verification (`npm run smoke`).
- Added repo hygiene and publish-ready README notes.
- Verified `npm run smoke` and `npm run build`.
- Published the app repo to GitHub: `https://github.com/jimmylegendary/agecraft-mobile-app`
