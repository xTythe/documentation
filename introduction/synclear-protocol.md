# Synclear Protocol

{% hint style="info" %}
The Synclear Dollar (SCD) is **not** the same as a fiat stablecoin like USDC, USDT, USD1, or PYUSD. SCD is a synthetic dollar (like Ethena's USDe or Falcon Finance's USDf), fully backed by crypto assets held in delta-neutral hedged positions and liquid stablecoins.\
\
This means the risks of interacting with SCD are inherently different. \
\
Please refer to our [Risk Disclosure](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/10/risk-disclosure) section before depositing.
{% endhint %}

Synclear is a two-layer synthetic dollar protocol built entirely on-chain. It issues _SCD_, a crypto-native dollar, and _stSCD_, its yield-bearing form, alongside a permissionless credit market where you borrow against your assets without selling them. Everything runs through pure DeFi venues, with no centralized custodian, no centralized exchange counterparty, and no KYC to mint SCD or borrow against it. Where other synthetic dollars reach scale by routing through centralized exchanges and custodians, Synclear keeps backing, custody, and hedging on-chain, and pairs the dollar with an on-chain credit market that no other synthetic dollar has.

You **mint** SCD by depositing USDC or USDT and receiving SCD 1:1, a direct swap available to anyone. The protocol puts that backing to work immediately while keeping it dollar-stable: a portion is deployed into delta-neutral hedged crypto positions that stay neutral to price, and the rest into stablecoin yield strategies and short-term instruments. Only a liquid buffer is held available for instant redemption; the rest of the backing is always working. _SCD_ is fully backed (subject to the discussion in the [Risk Disclosure](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/10/risk-disclosure) section regarding events that could result in loss of backing) and free to compose throughout on-chain finance.

_SCD_ is a stablecoin and does not earn yield on its own. To **earn**, stake _SCD_ for _stSCD_, the yield-bearing token that captures the return the protocol's backing generates across multiple cycle-tested DeFi venues, so payouts hold up across every market regime. Its highest-yielding strategy is run differently from other synthetic dollars: access to delta-neutral funding capture is not a flat benefit diluted across everyone, but a scarce, competitive position earned through on-chain arbitrageur safety and skill. The competition to hold those positions, and the funding on any left unclaimed, flow to stSCD holders directly. Alongside it, _stSCD_ earns lending interest on SCD Credit Markets, the Stability Pool (soft-liquidation fees and hard-liquidation bonuses from the SCD Credit Markets), and Fee Share (a portion of all protocol fees), with external lending-market interest and a baseline reserve of short-term instruments such as tokenized T-bills behind them as a backstop. To learn more about user-facing SCD flows, read [SCD User Mechanics](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/14/scd-user-mechanics). To learn more about Synclear's sustainable yield strategies and the concentrated yield from delta-neutral slots, visit [Yield & Asset Management](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/14/yield-and-asset-management).

**Borrowing** happens in the [SCD Credit Markets](https://app.gitbook.com/s/DJA9njN2uMlkeZuQfMaD/scd-credit-markets). You deposit crypto or yield-bearing collateral and borrow _SCD_ against it while keeping full ownership and price upside of that collateral. It is never sold or rehypothecated, and any native yield it earns remains yours. Borrowing terms improve automatically over time: Synclear scores on-chain credit behavior, and reliable participants earn higher LTV ratios and lower borrowing rates as their score grows. If collateral value falls, positions are converted gradually through soft liquidation rather than in a single liquidation event, and reverse automatically when the price recovers.\
\
These two layers are not separate products bolted together. They are one machine. The Yield Vault puts SCD to work and funds the credit markets; the credit markets create demand for _SCD_ and pay interest back to _stSCD_. Each layer earns on a different axis: the Yield Vault on funding and strategy yield, the credit markets on borrowing demand that rises when funding falls. That is why Synclear holds up across the full market cycle, and why it scales past the ceiling that limits a yield product alone. A synthetic dollar that is fully on-chain, permissionless to mint and borrow, credit-scored, and counter-cyclical by construction is not something the market has had before.

#### What you can do

Anyone can mint, borrow, and redeem on Synclear without permission or KYC. _SCD_ is a stablecoin, not a yield-bearing instrument, so only staking into _stSCD_ to earn protocol revenue is subject to jurisdictional restrictions.

* **Mint SCD.** Deposit USDC or USDT and receive SCD 1:1. Open to everyone, no KYC, no fees, no execution costs or slippage, and no counterparty approval.
* **Stake into stSCD.** Deposit _SCD_ into the SCD Yield Vaults to earn protocol revenue, or unstake at any time, with a fixed cooldown before the SCD is claimable, no queue. _Available only in permitted jurisdictions._
* **Borrow SCD.** Post blue-chip crypto (ETH, BTC, wstETH, PAXG, XAUt, and more) or yield-bearing collateral (Ethena's sUSDe, Sky's sUSDS, Aave's aUSDC, and more) into the SCD Credit Markets and draw _SCD_ against it, fully overcollateralized. Your collateral keeps its price upside and any native yield it already earns.
* **Trade SCD anywhere.** Acquire or exit _SCD_ freely on external pools such as Uniswap or Curve against USDC, USDT, and other assets.
* **Redeem & repay.** Burn _SCD_ to reclaim backing assets, or repay a loan to release your collateral in full.

> **Keep SCD at $1.** Anyone can arbitrage the peg: buy and redeem _SCD_ when it trades below a dollar, or mint and sell when it trades above. See [Stabilize SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/14/scd-mechanics/stabilize-scd) for how Peg Stability Arbitrage works.

#### Quick links

* How to mint SCD
* How to borrow against your assets
* [Protocol data & transparency dashboard](https://app.synclear.io/data)
* Frequently asked questions

{% hint style="info" %}
_SCD_ is a stablecoin, not a yield-bearing instrument. \
\
Minting, holding, trading, and borrowing _SCD_ are open to everyone, everywhere. Earning protocol yield by staking into _stSCD_ is the only action subject to jurisdictional restrictions. Users are responsible for compliance with the laws of their own jurisdiction.
{% endhint %}
