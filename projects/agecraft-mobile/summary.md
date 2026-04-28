# AgeCraft

- Project ID: agecraft-mobile
- Project objective: 현재 AgeCraft 3-era MVP prototype를 외부 플레이테스트 가능한 pre-alpha로 발전시키고 재미/경제/진행 가설을 검증한다
- Project status: done
- Root task group: tg-root
- Active snapshot: snapshot-root-v4
- Task groups: 1
- Task group versions: 4
- Tasks: 12
- Snapshots: 4
- Run nodes: 11
- Run edges: 10

## Task status counts
- pending: 0
- active: 0
- done: 12
- blocked: 0
- cancelled: 0

## Task groups
- tg-root — objective: 현재 AgeCraft 3-era MVP prototype를 외부 플레이테스트 가능한 pre-alpha로 발전시키고 재미/경제/진행 가설을 검증한다
  - version tgv-root-v1: 초기 루트 분해
  - version tgv-root-v2: 2D 모바일 MVP를 위한 1차 구조 분해
    - task task-core-loop-era-progression [done]: 핵심 플레이 루프와 시대 진화 구조 정의
    - task task-infinite-item-combination-system [done]: 무한 아이템 조합 및 희소성 시스템 설계
    - task task-nft-loyalty-economy [done]: NFT 소유권과 loyalty 경제 설계
    - task task-2d-mobile-mvp-scope [done]: 2D 모바일 MVP 범위와 구현 전략 정의
  - version tgv-root-v3: 설계 완료 후 구현 중심 execution plan
    - task task-build-playable-client [done]: 플레이 가능한 모바일 클라이언트 구축
    - task task-implement-crafting-economy-systems [done]: 조합 생성기와 경제 시스템 구현
    - task task-balance-and-content-pass [done]: 3개 시대 콘텐츠와 밸런스 패스 진행
    - task task-mvp-hardening-and-ship-readiness [done]: MVP 검증, 하드닝, 출시 준비
  - version tgv-root-v4 [selected]: 외부 플레이테스트 준비 pre-alpha objective
    - task task-tune-core-fun-and-pacing [done]: 핵심 재미 루프와 pacing 튜닝
    - task task-improve-mobile-onboarding-and-feedback [done]: 모바일 onboarding과 feedback 강화
    - task task-ship-shareable-playtest-build [done]: 공유 가능한 web playtest build 배포
    - task task-capture-feedback-and-next-iteration-plan [done]: 피드백 수집 구조와 다음 iteration plan 정의

## Selected version
- tg-root -> tgv-root-v4

## Run nodes
- node run-node-client-implementation [done] type=implementation sourceTask=task-build-playable-client
- node run-node-content-balance-pass [done] type=implementation sourceTask=task-balance-and-content-pass
- node run-node-design-pass [done] type=design
- node run-node-economy-implementation [done] type=implementation sourceTask=task-implement-crafting-economy-systems
- node run-node-feedback-plan [done] type=planning sourceTask=task-capture-feedback-and-next-iteration-plan
- node run-node-fun-pacing-pass [done] type=implementation sourceTask=task-tune-core-fun-and-pacing
- node run-node-hardening-and-ship [done] type=implementation sourceTask=task-mvp-hardening-and-ship-readiness
- node run-node-initial-structuring [done] type=planning
- node run-node-onboarding-feedback-pass [done] type=implementation sourceTask=task-improve-mobile-onboarding-and-feedback
- node run-node-playtest-deploy-blocker [done] type=planning sourceTask=task-ship-shareable-playtest-build
- node run-node-playtest-phase-planning [done] type=planning

## Run edges
- edge run-edge-client-to-economy-implementation: run-node-client-implementation -follows-> run-node-economy-implementation
- edge run-edge-content-to-hardening: run-node-content-balance-pass -follows-> run-node-hardening-and-ship
- edge run-edge-design-to-client-implementation: run-node-design-pass -follows-> run-node-client-implementation
- edge run-edge-economy-to-content-balance: run-node-economy-implementation -follows-> run-node-content-balance-pass
- edge run-edge-feedback-plan-to-deploy-blocker: run-node-feedback-plan -blocks-> run-node-playtest-deploy-blocker
- edge run-edge-fun-pacing-to-onboarding-feedback: run-node-fun-pacing-pass -follows-> run-node-onboarding-feedback-pass
- edge run-edge-hardening-to-playtest-planning: run-node-hardening-and-ship -follows-> run-node-playtest-phase-planning
- edge run-edge-onboarding-to-feedback-plan: run-node-onboarding-feedback-pass -follows-> run-node-feedback-plan
- edge run-edge-playtest-planning-to-fun-pacing: run-node-playtest-phase-planning -follows-> run-node-fun-pacing-pass
- edge run-edge-structuring-to-design: run-node-initial-structuring -follows-> run-node-design-pass
