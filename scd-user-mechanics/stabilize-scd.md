# Stabilize SCD

_SCD_ is designed to hold a value of one dollar, and two things keep it there. The capital backing behind each _SCD_ is held at a dollar of value, whether it sits in stablecoins or in a volatile asset paired with an offsetting short, so redemption can always return roughly a dollar. And because redemption returns a dollar, open-market arbitrage continuously pulls the traded price back whenever it drifts. The first half, how the backing is kept dollar-stable, is covered in [Synclear Dollar: SCD](../introduction/synclear-dollar-scd.md). This page covers the second: how the market price of _SCD_ is held at a dollar.

{% hint style="info" %}
The peg is held by open markets, not by discretion. Anyone can push _SCD_ back to a dollar at any time, with no permission, by arbitraging it against an always-open one-to-one redemption window.
{% endhint %}

#### Peg Stability Arbitrage

The price of _SCD_ is held by arbitrage through the same mint and redeem engine used to issue and exit it. When _SC&#x44;_&#x74;rades below a dollar (SCD < $1), anyone can buy it on the open market and redeem it through the protocol for a dollar of backing, keeping the difference. The buying lifts the price and the redemption removes _SCD_ from supply, both pushing it back toward a dollar. When _SCD_ trades above a dollar (SCD > $1), the reverse runs: mint fresh _SCD_ for a dollar of stablecoins and sell it on the market for more, which adds supply and pushes the price back down. The opportunity is open to everyone, runs continuously, and needs no approval.

What keeps the band tight is that the stablecoin lane (USDC and USDT) carries no protocol fee in either direction. Because the round trip is frictionless, the arbitrage stays profitable on even small deviations, so the price is pinned close to a dollar rather than to a dollar plus a toll. A fee on either leg would widen the band by exactly that much.

#### The instant redemption buffer

The below-a-dollar (SCD < $1) side of that arbitrage only works if redemption is fast and certain. The protocol holds a buffer of liquid stablecoins, USDC and USDT, inside the redeem engine that serves redemptions immediately, 1:1, with no fee, up to its capacity. This is the always-open window arbitrageurs rely on: a guaranteed instant exit at a dollar, which is what lets them close the gap the moment _SCD_ slips below peg. When redemptions run past the buffer, the remainder is served through the Withdrawal Queue as slower backing unwinds. Details covered [here](swap-scd.md).

#### A lean buffer, defended by a throttle

The buffer is kept deliberately lean. Synclear does not warehouse a large idle stablecoin reserve, because the backing is meant to stay productive rather than sitting idle waiting to be redeemed. That means the peg is not defended by sheer buffer size, and it does not need to be. Under normal conditions the lane is frictionless. Only when the buffer is drawn down under stress does a throttle engage, capping how much can be redeemed per block and reintroducing friction in proportion to the stress, layered with a circuit breaker (ERC-7265) that pauses outflows if they spike past a safe rate. The result is a window that stays open and free almost all of the time and slows only during a genuine run, which is exactly when slowing it protects the holders who remain. The throttle and breaker thresholds are set by protocol governance.

#### Emergency buyback

As a final, governance set backstop, the protocol can deploy its reserves to buy _SCD_ from the open market and support the price directly. This is a downside tool only. It is reserved for when _SCD_ trades materially below a dollar and stays there, a discount deep and persistent enough that open arbitrage and the redemption buffer are not closing it on their own. Buying _SCD_ back removes it from circulation and lifts the price. It is a last resort, bounded by the size of the reserve, and not the mechanism the peg relies on from day to day. The upside needs no equivalent: when _SCD_ trades above a dollar, open minting and selling adds supply and brings it back down, and an above-peg price does not threaten solvency the way a sustained discount can.
