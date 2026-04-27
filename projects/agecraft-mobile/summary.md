# AgeCraft

- Project ID: agecraft-mobile
- Project objective: 원시시대부터 미래 시대까지 진화하며 확률형 무한 조합 아이템 제작, NFT 소유권, loyalty 보상이 결합된 2D 모바일 게임 MVP를 설계하고 구현한다
- Project status: done
- Root task group: tg-root
- Active snapshot: snapshot-root-v3
- Task groups: 1
- Task group versions: 3
- Tasks: 8
- Snapshots: 3
- Run nodes: 6
- Run edges: 5

## Task status counts
- pending: 0
- active: 0
- done: 8
- blocked: 0
- cancelled: 0

## Task groups
- tg-root — objective: 원시시대부터 미래 시대까지 진화하며 확률형 무한 조합 아이템 제작, NFT 소유권, loyalty 보상이 결합된 2D 모바일 게임 MVP를 설계하고 구현한다
  - version tgv-root-v1: 초기 루트 분해
  - version tgv-root-v2: 2D 모바일 MVP를 위한 1차 구조 분해
    - task task-core-loop-era-progression [done]: 핵심 플레이 루프와 시대 진화 구조 정의
    - task task-infinite-item-combination-system [done]: 무한 아이템 조합 및 희소성 시스템 설계
    - task task-nft-loyalty-economy [done]: NFT 소유권과 loyalty 경제 설계
    - task task-2d-mobile-mvp-scope [done]: 2D 모바일 MVP 범위와 구현 전략 정의
  - version tgv-root-v3 [selected]: 설계 완료 후 구현 중심 execution plan
    - task task-build-playable-client [done]: 플레이 가능한 모바일 클라이언트 구축
    - task task-implement-crafting-economy-systems [done]: 조합 생성기와 경제 시스템 구현
    - task task-balance-and-content-pass [done]: 3개 시대 콘텐츠와 밸런스 패스 진행
    - task task-mvp-hardening-and-ship-readiness [done]: MVP 검증, 하드닝, 출시 준비

## Selected version
- tg-root -> tgv-root-v3

## Run nodes
- node run-node-client-implementation [done] type=implementation sourceTask=task-build-playable-client
- node run-node-content-balance-pass [done] type=implementation sourceTask=task-balance-and-content-pass
- node run-node-design-pass [done] type=design
- node run-node-economy-implementation [done] type=implementation sourceTask=task-implement-crafting-economy-systems
- node run-node-hardening-and-ship [done] type=implementation sourceTask=task-mvp-hardening-and-ship-readiness
- node run-node-initial-structuring [done] type=planning

## Run edges
- edge run-edge-client-to-economy-implementation: run-node-client-implementation -follows-> run-node-economy-implementation
- edge run-edge-content-to-hardening: run-node-content-balance-pass -follows-> run-node-hardening-and-ship
- edge run-edge-design-to-client-implementation: run-node-design-pass -follows-> run-node-client-implementation
- edge run-edge-economy-to-content-balance: run-node-economy-implementation -follows-> run-node-content-balance-pass
- edge run-edge-structuring-to-design: run-node-initial-structuring -follows-> run-node-design-pass
