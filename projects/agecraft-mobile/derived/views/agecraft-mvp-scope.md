# AgeCraft 2D mobile MVP scope and implementation strategy

## MVP question
Can we prove that players enjoy:
- short mobile gathering/crafting loops
- probabilistic breakthrough crafting
- getting stuck and choosing between self-crafting vs market purchase
- creator value through lineage and loyalty

## Recommended MVP shape
### Player-facing slice
- touch-first 2D mobile game
- 3 eras playable: Stone, Bronze, Classical
- 1 home camp screen
- 1 simple exploration/gather screen per era
- 1 crafting screen
- 1 market screen
- 1 inventory/lineage inspect screen

### Systems that must exist
- resource gathering
- inventory
- craft resolver
- era bottleneck checks
- progression unlocks
- creator attribution
- market listing/purchase
- loyalty accumulation

### Systems that can be mocked first
- real blockchain minting
- wallet connection
- external payments
- multiplayer synchronous world
- advanced social/chat layers

## Technical recommendation
For fastest delivery, use a **touch-first web stack that can later wrap to mobile**.
Recommended stack:
- Phaser 3 + TypeScript for 2D gameplay/client loop
- Vite for fast iteration
- local JSON/mock persistence first, then lightweight backend if needed
- PWA/mobile browser first, Capacitor wrapper later if retention is promising

Reason:
- faster than starting with on-chain/mobile-native complexity
- easy to iterate with AI coding agents
- enough to validate game feel and economy assumptions honestly

## Implementation phases
### Phase 1 — playable prototype
- gather resources
- craft items
- solve Stone Age bottleneck
- see lineage and rarity

### Phase 2 — progression loop
- add Bronze and Classical eras
- add market purchases
- add loyalty points
- add visible bottleneck goals

### Phase 3 — economy validation
- creator pages
- notable item mint-state simulation
- balance rarity vs usefulness
- retention and progression tuning

## Definition of MVP done
The MVP is done when a new player can:
1. start in Stone Age
2. gather and craft multiple times
3. hit a meaningful bottleneck
4. either craft through it or buy an item from the market
5. unlock the next era
6. understand that creators of useful items gain lasting value through loyalty

## Non-goals for the first release
- real-money token economy
- infinite era count in production
- fully trustless crafting proofs
- polished art pipeline beyond functional readability

## Immediate repo/workflow proposal
- keep TaskOps canonical project in the vault
- create implementation repo at `workspace/projects/agecraft-mobile-app`
- track implementation progress back into TaskOps run nodes and future task-group versions
