---
taskOpsVersion: v1
entityType: runNode
id: run-node-selfhosting-packaging
runId: run-main
type: implementation
title: docker compose self-hosting 구성 추가 진행
objective: repo에 Dockerfile, compose, web server config를 추가한다
status: done
sourceTaskId: task-add-docker-compose-self-hosting
sourceTaskGroupVersionId: tgv-root-v4
createdAt: 2026-04-28T04:16:30.000Z
---
# docker compose self-hosting 구성 추가 진행

- Dockerfile / nginx config / compose.yaml / .dockerignore를 추가했다.
- `HOST_PORT=18080 docker compose up -d --build`와 healthz/title check를 통과했다.
