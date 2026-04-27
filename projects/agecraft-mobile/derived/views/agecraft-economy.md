# AgeCraft NFT and loyalty economy

## Product stance
The fun loop must work before real on-chain complexity is mandatory.
So the MVP separates:
- **gameplay truth**: all items exist and function in-game first
- **ownership elevation**: only selected items are promoted to tradable NFT state

## Minting rule
Not every item should become an NFT.
A player may mint only when an item meets at least one condition:
- clears an era bottleneck above threshold
- reaches rarity score threshold
- is purchased enough times in the market
- is manually protected by the creator as a notable discovery

This avoids chain spam and focuses NFT value on socially meaningful items.

## Ownership layers
### Off-chain default
- all crafted items live in the game inventory database
- full lineage and creator ID are recorded
- market listing can happen inside the game economy first

### Elevated NFT state
- item is wrapped into a tokenized record
- token references immutable lineage hash + gameplay metadata snapshot
- item can still be used in-game by the owner or renter depending on market rule

## Loyalty reward rule
Whenever a player-created item is used in a meaningful downstream action, the original creator receives loyalty.
Meaningful actions:
- direct purchase
- rental/borrow use that clears progression
- use as ingredient in a higher-tier successful craft
- repeated use in high-era bottleneck solutions

## Loyalty payout model
Recommended MVP logic:
- buyer pays normal price
- creator receives one-time sale revenue
- creator also receives loyalty points from downstream qualifying uses
- loyalty converts into cosmetic prestige, market fee discounts, and limited premium crafting advantages

Later, loyalty could convert partly into revshare or token rewards, but MVP should not promise speculative yield.

## Anti-abuse rules
To prevent farm loops:
- creator cannot farm loyalty by self-trading between linked accounts without cost signals
- repeated low-value reuse should decay sharply
- only bottleneck-relevant or rarity-relevant uses generate full loyalty
- suspicious circular lineage patterns should reduce payout weight

## Market structure
MVP market surfaces:
- **browse**: search by era, function, rarity, creator
- **buy now**: fast path for bottleneck-solving items
- **creator card**: shows best discoveries and total loyalty reputation
- **lineage view**: shows what ingredients led to the item

## Why this ecosystem works
- crafters are rewarded for hitting rare useful outcomes
- stuck players can convert money or soft currency into time savings
- provenance matters because downstream usefulness compounds creator reputation
- the best items become social/economic landmarks, not just stat sticks

## MVP technical rule
Ship the first version with:
- off-chain inventory and market
- simulated mint state in the database
- lineage hash and creator attribution always present
- real chain integration behind a feature flag for later phases
