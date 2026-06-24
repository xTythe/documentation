# Redeem SCD

Redeeming is how SCD exits circulation. You swap SCD and reclaim a dollar of backing for each SCD, the reverse of minting, open to anyone with no KYC.

{% hint style="info" %}
Redemption returns roughly a dollar of backing per SCD. An instant buffer serves redemptions immediately and 1:1 up to its capacity. Larger redemptions are served through the Withdrawal Queue as slower backing unwinds.&#x20;
{% endhint %}

This page covers how redemption executes, the instant buffer and the Withdrawal Queue, the stress protections, the fees involved, and the alternative of exiting on the open market. For how redemption underpins the peg, see Stabilize SCD.

#### How redemption executes

Redemption is the reverse swap: burn SCD and reclaim a dollar of backing for each SCD. An instant USDC and USDT buffer held inside the mint-and-redeem engine serves redemptions immediately, at no fee, 1:1, up to its capacity.

When redemptions exceed the buffer, the remainder routes through the **Withdrawal Queue**: the protocol unwinds slower backing, such as open delta-neutral positions, to free stablecoins, and queued redemptions are served as that backing converts. The conservative core is highly liquid, so the queue is a stress-condition path rather than an everyday one.

#### A lean buffer, defended under stress

The buffer is kept deliberately lean. Synclear does not warehouse a large idle stablecoin reserve, because backing is meant to stay productive rather than sit waiting to be redeemed. The peg is not defended by buffer size, and does not need to be.

Under normal conditions the lane is frictionless. Only when the buffer is drawn down under stress does a throttle engage, capping how much can be redeemed per block in proportion to the stress, layered with a circuit breaker (ERC-7265) that pauses outflows if they spike past a safe rate. The result is an exit that stays open and free almost all of the time and slows only during a genuine run, which is exactly when slowing it protects the holders who remain. Throttle and breaker thresholds are set by governance.

#### Fees

* **Normal redemption.** No protocol fee. SCD redeems 1:1 through the instant buffer.
* **Redeeming beyond the buffer.** When redemptions exceed the instant buffer and must draw on slower backing, they queue and a **surge fee** proportional to queue depth applies, paid to the savers who remain. This is a stress-only mechanism, not a standing fee.

#### Exiting on the open market

You can also exit SCD without redeeming, by trading it on external AMM pools such as Uniswap, Aerodrome, or Curve against USDC, USDT, and other assets. Redeeming swaps with the protocol at par; trading sells on the open market at whatever price it is quoting. When SCD is at peg the two are equivalent. When it trades below a dollar, redeeming at par is the better exit, and that gap is exactly the arbitrage that restores the peg, covered in Stabilize SCD.
