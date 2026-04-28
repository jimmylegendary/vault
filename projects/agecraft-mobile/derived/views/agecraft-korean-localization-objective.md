# AgeCraft next objective: Korean-first playtest build

## Objective
Turn the current AgeCraft pre-alpha into a **Korean-first playtest build** so a Korean-speaking tester can understand the loop, item value, and progression without English UI friction.

## Success criteria
A Korean-speaking tester should be able to:
1. understand the first-minute onboarding entirely in Korean
2. read item / gate / market feedback in Korean without mixing core UX copy back into English
3. play through the current 3-era run in Korean
4. open the same live shareable build URL after redeploy and see the Korean-localized version

## Scope rule
- prioritize player-facing copy first
- keep internal code/data identifiers in English if that is cleaner
- preserve the existing game structure, smoke gate, and deploy path

## Exit condition
This phase is complete when:
- the player-facing UI is Korean-first
- smoke/build still pass
- the Vercel build is redeployed successfully
- GitHub repo and TaskOps vault records are both updated
