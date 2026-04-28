---
taskOpsVersion: v1
entityType: task
id: task-write-internal-serving-guide-and-verify
taskGroupId: tg-root
taskGroupVersionId: tgv-root-v4
title: 사내 serving 가이드 작성 및 검증
objective: 운영자가 clone 후 compose로 띄우는 절차와 주의사항을 문서화하고 검증 결과를 남긴다.
responsibility: guide/documentation과 실행 검증 정리
completionCriteria: README 또는 별도 guide에 내부 배포 절차가 정리되고 로컬 검증까지 끝난다.
order: 2
createdAt: 2026-04-28T04:12:18.000Z
status: done
---
# 사내 serving 가이드 작성 및 검증

- `SELF_HOSTING.md`를 추가하고 README에 compose self-hosting 경로를 연결했다.
- healthz / title check까지 포함한 로컬 검증을 마쳤다.
