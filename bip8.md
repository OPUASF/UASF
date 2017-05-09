# BIP8 FAQ

### What is BIP8?

BIP8 is a modification to BIP9.  BIP9 was the deployment mechanism for soft forks in the past that relied on miners signalling 95% readiness for activation.  It was successfully used to activate BIP65 (OP_CHECKLOCKTIMEVERIFY) and BIP68/BIP112/BIP113 (CHECKSEQUENCEVERIFY/Median Time).  BIP9 allows for upgrades to the system whenever a supermajority of miners are ready to enforce the changes, allowing for faster upgrades than a UASF may allow.  Every 2016 blocks, if 95% of those blocks signalled readiness for the proposed change, the soft fork enforcement would become mandatory in 2016 blocks.  Each change is given a fixed timeframe to achieve this activation, such that any change that is not activated may have its bit reused.  Proposals that do not achieve activation expire at the end of their time period, but may be renewed if there is sufficient interest.

BIP8 modifies BIP9 to automatically convert into a UASF at the end of its activation time.  This avoids the problem of a miner veto while still allowing miners to begin enforcing the rules sooner than a pure UASF would allow.  Once the final period completes after the timeout period, the rules become mandatory, regardless of signalling.

### Can BIP8 be applied to SegWit?

There was a proposal made by Shaolinfry to use BIP8 to deploy SegWit.  The proposal would set a new version bit for deployment after the current proposal would expire, and would lock-in in July 2018.  Miners would still be able to activate SegWit prior to the this date, but failure to activate would result in a mandatory lock-in.

Unlike BIP148, this proposal would not require miners to signal version bits for SegWit or create SegWit blocks. The only requirement for miners is to not build on top of blocks that are invalid under the SegWit rules.

### Can BIP8 result in chain splits?

Soft forks rely on the economic incentives of the majority of miners and economic actors to reject invalid blocks based on the new ruleset. Since the new BIP148 rules are a stricter set than the old rules, any chain split means the chain with the old rules would be in danger of being wiped out. If the majority of miners enforce the new ruleset, all blocks produced that are invalid in the new ruleset will become orphaned. This economic incentive pushes miners to enforce the new rules. A UASF uses similar economic incentives. If the majority of hashing power enforces the new rules, chain splits remain temporary as with a solely miner enforced soft fork.

If the majority of hashpower does not enforce the rules, a chain split would occur. If there is a greater demand for the blocks produced by the BIP148 miners, then profit-driven miners would eventually flock to this chain, leading to the orphaning of the pre-soft-fork chain. If the demand is less for the soft-fork chain, then both chains may co-exist indefinitely.

### Does node count determine activation?

No. Users that decide to enforce the new rules will only follow blocks that conform to the existing rules which will in turn cause miners to activate SegWit. A UASF could be enforced by any number of economic nodes, although hash power may only choose to follow such rules if there was significant economic weight behind it.
