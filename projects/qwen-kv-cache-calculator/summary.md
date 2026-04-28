# Qwen KV Cache Calculator

- Project ID: qwen-kv-cache-calculator
- Project objective: 계산기 repo를 사내에서 docker compose 기반으로 self-hosting 가능한 형태로 확장하고 운영 가이드를 제공한다
- Project status: done
- Root task group: tg-root
- Active snapshot: snapshot-root-v4
- Task groups: 1
- Task group versions: 4
- Tasks: 7
- Snapshots: 4
- Run nodes: 10
- Run edges: 9

## Task status counts
- pending: 0
- active: 0
- done: 7
- blocked: 0
- cancelled: 0

## Task groups
- tg-root — objective: 계산기 repo를 사내에서 docker compose 기반으로 self-hosting 가능한 형태로 확장하고 운영 가이드를 제공한다
  - version tgv-root-v1: 초기 루트 분해
  - version tgv-root-v2: Qwen3.5-27B KV cache research, calculator, and deploy plan
    - task task-research-model-spec-and-derive-kv-math [done]: 모델 스펙 확인 및 KV cache 계산식 도출
    - task task-build-interactive-kv-calculator-webpage [done]: 실시간 KV cache 계산 웹페이지 구현
    - task task-verify-deploy-and-report [done]: 검증, 배포, 보고
  - version tgv-root-v3: target system / serving param 확장 objective
    - task task-extend-calculator-for-system-topology [done]: TP/DP/EP 및 serving topology 확장
    - task task-reverify-and-redeploy-extended-calculator [done]: 확장 계산기 재검증 및 재배포
  - version tgv-root-v4 [selected]: docker compose self-hosting extension objective
    - task task-add-docker-compose-self-hosting [done]: docker compose self-hosting 구성 추가
    - task task-write-internal-serving-guide-and-verify [done]: 사내 serving 가이드 작성 및 검증

## Selected version
- tg-root -> tgv-root-v4

## Run nodes
- node run-node-calculator-implementation [done] type=implementation sourceTask=task-build-interactive-kv-calculator-webpage
- node run-node-deploy-and-report [done] type=implementation sourceTask=task-verify-deploy-and-report
- node run-node-repo-rename [done] type=operations sourceTask=task-reverify-and-redeploy-extended-calculator
- node run-node-research-and-math [done] type=research sourceTask=task-research-model-spec-and-derive-kv-math
- node run-node-selfhosting-guide [done] type=documentation sourceTask=task-write-internal-serving-guide-and-verify
- node run-node-selfhosting-packaging [done] type=implementation sourceTask=task-add-docker-compose-self-hosting
- node run-node-selfhosting-planning [done] type=planning
- node run-node-topology-extension-pass [done] type=implementation sourceTask=task-extend-calculator-for-system-topology
- node run-node-topology-extension-planning [done] type=planning
- node run-node-topology-redeploy [done] type=implementation sourceTask=task-reverify-and-redeploy-extended-calculator

## Run edges
- edge run-edge-deploy-to-repo-rename: run-node-topology-redeploy -follows-> run-node-repo-rename
- edge run-edge-implementation-to-deploy: run-node-calculator-implementation -follows-> run-node-deploy-and-report
- edge run-edge-research-to-implementation: run-node-research-and-math -follows-> run-node-calculator-implementation
- edge run-edge-selfhosting-packaging-to-guide: run-node-selfhosting-packaging -follows-> run-node-selfhosting-guide
- edge run-edge-selfhosting-planning-to-packaging: run-node-selfhosting-planning -follows-> run-node-selfhosting-packaging
- edge run-edge-v2-complete-to-v3-planning: run-node-deploy-and-report -follows-> run-node-topology-extension-planning
- edge run-edge-v3-complete-to-selfhosting-planning: run-node-topology-redeploy -follows-> run-node-selfhosting-planning
- edge run-edge-v3-extension-to-redeploy: run-node-topology-extension-pass -follows-> run-node-topology-redeploy
- edge run-edge-v3-planning-to-extension: run-node-topology-extension-planning -follows-> run-node-topology-extension-pass
