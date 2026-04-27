# AgeCraft core loop and era progression

## One-session loop
1. **Scout**: player enters the current era map and gathers 3-5 base resources through short touch interactions.
2. **Craft**: player combines any owned items/resources in the camp forge.
3. **Evaluate**: output item reveals utility stats, rarity traits, and one or more era affinities.
4. **Decide**:
   - equip/use item to clear the current bottleneck
   - keep item as a future ingredient
   - list it on the market
   - buy an item created by another player if self-crafting is too slow
5. **Break through**: when the player solves the current bottleneck, the next era unlock meter advances.
6. **Loop**: the next era introduces new resources, recipes, and gating problems, which feed back into scouting and crafting.

## Era ladder
- **Stone Age**: survival basics, fire, sharp tools, shelter.
- **Bronze Age**: metallurgy, farming acceleration, transport.
- **Classical Age**: engineering, trade, military utility, written knowledge.
- **Industrial Age**: machines, fuel, mass production.
- **Digital Age**: computation, networks, automation.
- **Post-Digital / Future Age**: biotech, energy mastery, synthetic matter, temporal/planetary scale systems.

Each era adds:
- new raw resource families
- new trait pools
- more recipe slots/catalysts
- stronger bottleneck constraints
- higher-value market demand for breakthrough items

## Bottleneck model
Each era has 2-3 bottleneck archetypes:
- **resource bottleneck**: need efficiency or yield
- **capability bottleneck**: need a specific function such as cutting, heat, power, or computation
- **stability bottleneck**: need a high enough quality/reliability score

A stage is blocked until the player provides either:
- a self-crafted qualifying item, or
- a purchased qualifying item from the market

## Why the market matters
At later eras, useful outputs become statistically rare because success depends on:
- compatible material signatures
- correct catalyst timing
- enough stability to survive recombination
- rare trait alignment with the active bottleneck

That means progress has two honest routes:
1. spend time crafting until a qualifying item appears
2. buy a qualifying item from another player who already hit the roll

## Era unlock conditions
A new era unlocks when all are true:
- current era bottleneck score target is met
- player has crafted or acquired at least one era-defining item
- player has enough era knowledge points from repeated crafting/use

## MVP progression pacing
- each era should be clearable in 5-12 minutes in the first mobile MVP
- first public MVP ships with 3 playable eras:
  - Stone
  - Bronze
  - Classical
- Industrial+ remain visible in the roadmap/progression preview but locked

## Design rules
- every craft should either improve knowledge, inventory optionality, or market opportunity
- failure should still produce salvage or discovery value
- the player should feel stuck only in a way that suggests a response: craft, buy, or pivot ingredients
- hard progression should come from bottleneck requirements, not grind-only timers
