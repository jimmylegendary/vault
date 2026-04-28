# Qwen KV Cache Calculator

- Project ID: qwen-kv-cache-calculator
- Project objective: Qwen3.5-27B 모델의 A100 기준 KV cache 요구량을 계산하고, 파라미터를 바꿔 실시간으로 계산할 수 있는 웹 계산기를 만들고 배포한다
- Project status: done
- Root task group: tg-root
- Active snapshot: snapshot-root-v2
- Task groups: 1
- Task group versions: 2
- Tasks: 3
- Snapshots: 2
- Run nodes: 3
- Run edges: 2

## Task status counts
- pending: 0
- active: 0
- done: 3
- blocked: 0
- cancelled: 0

## Task groups
- tg-root — objective: Qwen3.5-27B 모델의 A100 기준 KV cache 요구량을 계산하고, 파라미터를 바꿔 실시간으로 계산할 수 있는 웹 계산기를 만들고 배포한다
  - version tgv-root-v1: 초기 루트 분해
  - version tgv-root-v2 [selected]: Qwen3.5-27B KV cache research, calculator, and deploy plan
    - task task-research-model-spec-and-derive-kv-math [done]: 모델 스펙 확인 및 KV cache 계산식 도출
    - task task-build-interactive-kv-calculator-webpage [done]: 실시간 KV cache 계산 웹페이지 구현
    - task task-verify-deploy-and-report [done]: 검증, 배포, 보고

## Selected version
- tg-root -> tgv-root-v2

## Run nodes
- node run-node-calculator-implementation [done] type=implementation sourceTask=task-build-interactive-kv-calculator-webpage
- node run-node-deploy-and-report [done] type=implementation sourceTask=task-verify-deploy-and-report
- node run-node-research-and-math [done] type=research sourceTask=task-research-model-spec-and-derive-kv-math

## Run edges
- edge run-edge-implementation-to-deploy: run-node-calculator-implementation -follows-> run-node-deploy-and-report
- edge run-edge-research-to-implementation: run-node-research-and-math -follows-> run-node-calculator-implementation
