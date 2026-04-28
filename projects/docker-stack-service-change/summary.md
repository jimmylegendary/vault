# Docker Stack Service Change Guide

- Project ID: docker-stack-service-change
- Project objective: Docker Swarm stack에서 기존 서비스 A/C를 중단하지 않고 새 서비스 D를 추가하고 필요시 B를 제거하는 안전한 배포 절차를 정리한다
- Project status: done
- Root task group: tg-root
- Active snapshot: snapshot-root-v2
- Task groups: 1
- Task group versions: 2
- Tasks: 1
- Snapshots: 2
- Run nodes: 1
- Run edges: 0

## Task status counts
- pending: 0
- active: 0
- done: 1
- blocked: 0
- cancelled: 0

## Task groups
- tg-root — objective: Docker Swarm stack에서 기존 서비스 A/C를 중단하지 않고 새 서비스 D를 추가하고 필요시 B를 제거하는 안전한 배포 절차를 정리한다
  - version tgv-root-v1: 초기 루트 분해
  - version tgv-root-v2 [selected]: Docker stack service add/remove runbook
    - task task-document-safe-deploy-path [done]: A/C 무중단 기준 안전한 deploy 경로 문서화

## Selected version
- tg-root -> tgv-root-v2

## Run nodes
- node run-node-stack-runbook [done] type=documentation sourceTask=task-document-safe-deploy-path

## Run edges
- 없음
