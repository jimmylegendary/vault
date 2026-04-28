# AgeCraft

- Project ID: agecraft-mobile
- Project objective: 실제 플레이 중 입력이 먹었다는 확신을 주는 interaction feedback 효과를 추가하고 다시 배포한다
- Project status: done
- Root task group: tg-root
- Active snapshot: snapshot-root-v7
- Task groups: 1
- Task group versions: 7
- Tasks: 18
- Snapshots: 7
- Run nodes: 19
- Run edges: 18

## Task status counts
- pending: 0
- active: 1
- done: 17
- blocked: 0
- cancelled: 0

## Task groups
- tg-root — objective: 실제 플레이 중 입력이 먹었다는 확신을 주는 interaction feedback 효과를 추가하고 다시 배포한다
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
  - version tgv-root-v4: 외부 플레이테스트 준비 pre-alpha objective
    - task task-tune-core-fun-and-pacing [done]: 핵심 재미 루프와 pacing 튜닝
    - task task-improve-mobile-onboarding-and-feedback [done]: 모바일 onboarding과 feedback 강화
    - task task-ship-shareable-playtest-build [done]: 공유 가능한 web playtest build 배포
    - task task-capture-feedback-and-next-iteration-plan [done]: 피드백 수집 구조와 다음 iteration plan 정의
  - version tgv-root-v5: 한글화 및 재배포 objective
    - task task-localize-player-facing-copy-ko [done]: 플레이어 노출 문구 한글화
    - task task-redeploy-korean-playtest-build [done]: 한글화 빌드 재배포 및 공유 상태 갱신
  - version tgv-root-v6: 모바일 interaction blocker 수정 objective
    - task task-fix-mobile-interaction-blocker [done]: 모바일 interaction blocker 수정
    - task task-reverify-and-redeploy-interaction-fix [done]: interaction 수정 재검증 및 재배포
  - version tgv-root-v7 [selected]: interaction feedback 강화 objective
    - task task-add-interaction-feedback-effects [active]: interaction feedback 효과 추가
    - task task-reverify-redeploy-feedback-effects [done]: feedback 효과 재검증 및 재배포

## Selected version
- tg-root -> tgv-root-v7

## Run nodes
- node run-node-client-implementation [done] type=implementation sourceTask=task-build-playable-client
- node run-node-content-balance-pass [done] type=implementation sourceTask=task-balance-and-content-pass
- node run-node-design-pass [done] type=design
- node run-node-economy-implementation [done] type=implementation sourceTask=task-implement-crafting-economy-systems
- node run-node-feedback-effects-pass [done] type=implementation sourceTask=task-add-interaction-feedback-effects
- node run-node-feedback-effects-planning [done] type=planning
- node run-node-feedback-effects-redeploy [done] type=implementation sourceTask=task-reverify-redeploy-feedback-effects
- node run-node-feedback-plan [done] type=planning sourceTask=task-capture-feedback-and-next-iteration-plan
- node run-node-fun-pacing-pass [done] type=implementation sourceTask=task-tune-core-fun-and-pacing
- node run-node-hardening-and-ship [done] type=implementation sourceTask=task-mvp-hardening-and-ship-readiness
- node run-node-initial-structuring [done] type=planning
- node run-node-interaction-debug [done] type=implementation sourceTask=task-fix-mobile-interaction-blocker
- node run-node-interaction-redeploy [done] type=implementation sourceTask=task-reverify-and-redeploy-interaction-fix
- node run-node-korean-localization-pass [done] type=implementation sourceTask=task-localize-player-facing-copy-ko
- node run-node-korean-localization-planning [done] type=planning
- node run-node-korean-redeploy [done] type=implementation sourceTask=task-redeploy-korean-playtest-build
- node run-node-onboarding-feedback-pass [done] type=implementation sourceTask=task-improve-mobile-onboarding-and-feedback
- node run-node-playtest-deploy-blocker [done] type=planning sourceTask=task-ship-shareable-playtest-build
- node run-node-playtest-phase-planning [done] type=planning

## Run edges
- edge run-edge-client-to-economy-implementation: run-node-client-implementation -follows-> run-node-economy-implementation
- edge run-edge-content-to-hardening: run-node-content-balance-pass -follows-> run-node-hardening-and-ship
- edge run-edge-design-to-client-implementation: run-node-design-pass -follows-> run-node-client-implementation
- edge run-edge-economy-to-content-balance: run-node-economy-implementation -follows-> run-node-content-balance-pass
- edge run-edge-feedback-effects-pass-to-redeploy: run-node-feedback-effects-pass -follows-> run-node-feedback-effects-redeploy
- edge run-edge-feedback-effects-planning-to-pass: run-node-feedback-effects-planning -follows-> run-node-feedback-effects-pass
- edge run-edge-feedback-plan-to-deploy-blocker: run-node-feedback-plan -blocks-> run-node-playtest-deploy-blocker
- edge run-edge-fun-pacing-to-onboarding-feedback: run-node-fun-pacing-pass -follows-> run-node-onboarding-feedback-pass
- edge run-edge-hardening-to-playtest-planning: run-node-hardening-and-ship -follows-> run-node-playtest-phase-planning
- edge run-edge-interaction-debug-to-redeploy: run-node-interaction-debug -follows-> run-node-interaction-redeploy
- edge run-edge-interaction-fix-to-feedback-effects-planning: run-node-interaction-redeploy -follows-> run-node-feedback-effects-planning
- edge run-edge-korean-localization-to-redeploy: run-node-korean-localization-pass -follows-> run-node-korean-redeploy
- edge run-edge-korean-planning-to-localization-pass: run-node-korean-localization-planning -follows-> run-node-korean-localization-pass
- edge run-edge-korean-redeploy-to-interaction-debug: run-node-korean-redeploy -follows-> run-node-interaction-debug
- edge run-edge-onboarding-to-feedback-plan: run-node-onboarding-feedback-pass -follows-> run-node-feedback-plan
- edge run-edge-playtest-complete-to-korean-planning: run-node-playtest-deploy-blocker -follows-> run-node-korean-localization-planning
- edge run-edge-playtest-planning-to-fun-pacing: run-node-playtest-phase-planning -follows-> run-node-fun-pacing-pass
- edge run-edge-structuring-to-design: run-node-initial-structuring -follows-> run-node-design-pass
