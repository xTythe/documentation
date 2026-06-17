# Stake SCD

Staking turns _SCD_ into _stSCD_, its yield-bearing form. _SCD_ held on its own earns nothing; _stSCD_ captures the return the protocol's backing generates and pays it to you continuously.

{% hint style="info" %}
_SCD_ is free and permissionless to mint, hold, borrow, trade, and redeem anywhere. Staking for _stSCD_ to earn protocol yield is the only action subject to jurisdictional restrictions. You are responsible for compliance with your own local laws.
{% endhint %}

This page covers how staking works, how _stSCD_ accrues value, and how to unstake. For where the yield itself comes from, see [Yield & Asset Management](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/14/yield-and-asset-management).

#### Staking: SCD for stSCD

You deposit _SCD_ and receive _stSCD_ in return at a 1:1 rate, a single token that represents your share of the staked pool.

* **One token, rising value.** _stSCD_ does not change in quantity. Instead, each _stSCD_ becomes redeemable for more _SCD_ over time as yield accrues. Your balance stays the same; what it is worth grows.
* **Yield accrues smoothly.** Earnings vest into the _stSCD_ value gradually rather than in jumps, so no one can stake just before a payout, capture it, and leave. You earn for the time you are actually staked.
* **One unified stSCD.** Every deposit stakes into the same _stSCD_, whatever asset originally backed it. The protocol isolates risk at the backing level, not by splitting the yield token.

#### What stSCD earns

Holding _stSCD_ is the passive way to earn from the protocol, and it is built to pay across market regimes rather than only when one strategy is strong. Its return is drawn from the protocol's whole diversified engine, several sources that do not rise and fall together, so _stSCD_ keeps earning when any single one is weak. Underneath them sits a base of steady, low-volatility income from lending and short-term instruments that does not depend on crypto funding at all. When funding markets cool, returns settle toward that base rather than toward zero, while lending demand and protocol fees rise into the gap. That is the base returns fall back to when the rest of the engine quiets, and it is what keeps _stSCD_ earning across the cycle.

_stSCD_ also shares in the protocol's delta-neutral funding market without competing in it. It earns the protocol's cut of that market, and whenever funding capacity is not fully claimed, the unclaimed funding flows back to _stSCD_ directly. So _stSCD_ keeps a line into funding yield: what it does not hold is the concentrated position.

That concentrated position is the funding-capture slot, a competitive tier for participants who want maximum funding exposure and will compete to hold it. It is not a fixed-size club. Slot capacity, both the amount deployable and the number of participants, grows as on-chain open interest and liquidity deepen, so the tier expands with the market rather than staying capped.

Returns are variable and uncapped, with no fixed or guaranteed rate. How all of this is produced, split, and scaled over time is covered in [Yield & Asset Management](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/14/yield-and-asset-management).

#### Unstaking: stSCD for SCD

Unstaking converts _stSCD_ back into _SCD_ at its current accrued value. It is not instant. Two protections sit on either side of holding _stSCD_: yield vests gradually so no one can time their entry to capture it, and unstaking carries a cooldown so no one can rush the exit at the cost of the holders who stay. During the cooldown the _SCD_ is held before it is released. The cooldown period is set by the protocol.

Unstaking _stSCD_ and redeeming _SCD_ are two separate steps with two separate waiting mechanisms. The cooldown above applies only to unstaking, which returns _SCD_ and nothing further. Redeeming that _SCD_ for its underlying backing is a different process on the mint and redeem engine, with its own instant buffer and a queue mechanism for when slower backing has to unwind. Once you hold _SCD_ you can also just keep it or use it across DeFi rather than redeem. The full redemption flow can be found on the [Swap SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/14/scd-user-mechanics/swap-scd) page.
