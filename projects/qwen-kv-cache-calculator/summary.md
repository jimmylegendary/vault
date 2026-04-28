# Qwen KV Cache Calculator

- Project ID: qwen-kv-cache-calculator
- Project objective: Qwen KV cache 계산기에 target system 구성과 serving param을 추가해서 per-GPU / per-replica / cluster 관점으로 계산 가능하게 확장한다
- Project status: done
- Root task group: tg-root
- Active snapshot: snapshot-root-v3
- Task groups: 1
- Task group versions: 3
- Tasks: 5
- Snapshots: 3
- Run nodes: 7
- Run edges: 6

## Task status counts
- pending: 0
- active: 0
- done: 5
- blocked: 0
- cancelled: 0

## Task groups
- tg-root — objective: Qwen KV cache 계산기에 target system 구성과 serving param을 추가해서 per-GPU / per-replica / cluster 관점으로 계산 가능하게 확장한다
  - version tgv-root-v1: 초기 루트 분해
  - version tgv-root-v2: Qwen3.5-27B KV cache research, calculator, and deploy plan
    - task task-research-model-spec-and-derive-kv-math [done]: 모델 스펙 확인 및 KV cache 계산식 도출
    - task task-build-interactive-kv-calculator-webpage [done]: 실시간 KV cache 계산 웹페이지 구현
    - task task-verify-deploy-and-report [done]: 검증, 배포, 보고
  - version tgv-root-v3 [selected]: target system / serving param 확장 objective
    - task task-extend-calculator-for-system-topology [done]: TP/DP/EP 및 serving topology 확장
    - task task-reverify-and-redeploy-extended-calculator [done]: 확장 계산기 재검증 및 재배포

## Selected version
- tg-root -> tgv-root-v3

## Run nodes
- node run-node-calculator-implementation [done] type=implementation sourceTask=task-build-interactive-kv-calculator-webpage
- node run-node-deploy-and-report [done] type=implementation sourceTask=task-verify-deploy-and-report
- node run-node-repo-rename [done] type=operations sourceTask=task-reverify-and-redeploy-extended-calculator
- node run-node-research-and-math [done] type=research sourceTask=task-research-model-spec-and-derive-kv-math
- node run-node-topology-extension-pass [done] type=implementation sourceTask=task-extend-calculator-for-system-topology
- node run-node-topology-extension-planning [done] type=planning
- node run-node-topology-redeploy [done] type=implementation sourceTask=task-reverify-and-redeploy-extended-calculator

## Run edges
- edge run-edge-deploy-to-repo-rename: run-node-topology-redeploy -follows-> run-node-repo-rename
- edge run-edge-implementation-to-deploy: run-node-calculator-implementation -follows-> run-node-deploy-and-report
- edge run-edge-research-to-implementation: run-node-research-and-math -follows-> run-node-calculator-implementation
- edge run-edge-v2-complete-to-v3-planning: run-node-deploy-and-report -follows-> run-node-topology-extension-planning
- edge run-edge-v3-extension-to-redeploy: run-node-topology-extension-pass -follows-> run-node-topology-redeploy
- edge run-edge-v3-planning-to-extension: run-node-topology-extension-planning -follows-> run-node-topology-extension-pass
