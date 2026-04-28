---
taskOpsVersion: v1
entityType: task
id: task-reverify-and-redeploy-extended-calculator
taskGroupId: tg-root
taskGroupVersionId: tgv-root-v3
title: 확장 계산기 재검증 및 재배포
objective: 확장된 계산기를 브라우저에서 검증하고 다시 배포한다.
responsibility: 검증, 배포, 기록 갱신
completionCriteria: 로컬/라이브 검증을 통과하고 GitHub/Vercel/vault가 최신 상태가 된다.
order: 2
createdAt: 2026-04-28T03:22:12.469Z
status: done
---
# 확장 계산기 재검증 및 재배포

- App repo push 완료.
- GitHub repo renamed to `https://github.com/jimmylegendary/kv-cache-calculator`
- Vercel redeploy 완료: `https://qwen-kv-cache-calculator-app.vercel.app`
- Local/live Playwright verification 완료.
