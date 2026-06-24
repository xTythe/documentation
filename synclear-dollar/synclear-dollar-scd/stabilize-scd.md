# Stabilize SCD

SCD is designed to hold a value of one dollar, and two things keep it there. The capital backing behind each SCD is held at a dollar of value, so redemption can always return roughly a dollar, and because redemption returns a dollar, open-market arbitrage continuously pulls the traded price back whenever it drifts. The first half, how the backing is kept dollar-stable, is covered in Synclear Dollar (SCD). This page covers the second: how the market price of SCD is held at a dollar.

{% hint style="info" %}
The peg is held by open markets, not by discretion. Anyone can push SCD back to a dollar at any time, with no permission, by arbitraging it against an always-open 1:1 redemption window.
{% endhint %}

#### Peg stability arbitrage

The price of SCD is held by arbitrage through the same mint-and-redeem engine used to issue and exit it.

When SCD trades **below a dollar**, anyone can buy it on the open market and redeem it through the protocol for a dollar of backing, keeping the difference. The buying lifts the price and the redemption removes SCD from supply, both pushing it back toward a dollar.

When SCD trades **above a dollar**, the reverse runs: mint fresh SCD for a dollar of stablecoins and sell it on the market for more, which adds supply and pushes the price back down.

The opportunity is open to everyone, runs continuously, and needs no approval.

#### Why the band stays tight

What keeps the band tight is that the stablecoin lane, USDC and USDT, carries **no protocol fee in either direction**. Because the round trip is frictionless, the arbitrage stays profitable on even small deviations, so the price is pinned close to a dollar rather than to a dollar plus a toll. A fee on either leg would widen the band by exactly that much.

#### The redemption window

The below-a-dollar side of the arbitrage depends on a fast, certain exit at par. That is the instant 1:1 redemption buffer, the always-open window arbitrageurs rely on to close the gap the moment SCD slips below peg. The buffer is kept deliberately lean, and under stress it throttles to protect the holders who remain. Its capacity, the Withdrawal Queue, and the stress protections are detailed in Redeem SCD. What matters for the peg is that the window is open and frictionless in normal conditions, which is what keeps the arbitrage continuous.

#### Emergency buyback

As a final, governance-set backstop, the protocol can deploy its reserve to buy SCD from the open market and support the price directly. This is a downside tool only. It is reserved for when SCD trades materially below a dollar and stays there, a discount deep and persistent enough that open arbitrage and the redemption buffer are not closing it on their own. Buying SCD back removes it from circulation and lifts the price. It is a last resort, bounded by the size of the reserve, and not the mechanism the peg relies on from day to day.

The upside needs no equivalent: when SCD trades above a dollar, open minting and selling adds supply and brings it back down, and an above-peg price does not threaten solvency the way a sustained discount can.
