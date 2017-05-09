# BIP8 FAQ

### What is BIP8?

### How is BIP8 different than BIP9?

### Can BIP8 result in chain splits?

Soft forks rely on the economic incentives of the majority of miners and economic actors to reject invalid blocks based on the new ruleset. Since the new BIP148 rules are a stricter set than the old rules, any chain split means the chain with the old rules would be in danger of being wiped out. If the majority of miners enforce the new ruleset, all blocks produced that are invalid in the new ruleset will become orphaned. This economic incentive pushes miners to enforce the new rules. A UASF uses similar economic incentives. If the majority of hashing power enforces the new rules, chain splits remain temporary as with a solely miner enforced soft fork.

If the majority of hashpower does not enforce the rules, a chain split would occur. If there is a greater demand for the blocks produced by the BIP148 miners, then profit-driven miners would eventually flock to this chain, leading to the orphaning of the pre-soft-fork chain. If the demand is less for the soft-fork chain, then both chains may co-exist indefinitely.

### Does node count determine activation?

No. Users that decide to enforce the new rules will only follow blocks that conform to the existing rules which will in turn cause miners to activate SegWit. A UASF could be enforced by any number of economic nodes, although hash power may only choose to follow such rules if there was significant economic weight behind it.
