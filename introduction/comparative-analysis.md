# Comparative Analysis

Synclear did not invent the synthetic dollar. It builds on a lineage of protocols that each solved part of the problem, and it is designed to occupy the space they left open: a fully on-chain, permissionless dollar that scales with decentralized markets rather than depending on centralized ones.

#### Why stablecoins matter

Stablecoins are the most-used instrument in crypto. The large majority of trading pairs across spot and derivatives venues are denominated in them, they settle trillions of dollars on-chain, and they are the only crypto asset to have found durable, global product-market fit with over 100 million users. They are the foundation the rest of the industry is built on, and the largest single market crypto addresses.

That foundation still has structural gaps, in both the centralized and the decentralized models.

#### The centralized model and its limits

Fiat-backed stablecoins like USDC and USDT are stable and capital-efficient, but they carry costs the holder does not choose:

* **Custodial and banking dependency.** The backing sits in bonds and regulated bank accounts, exposed to censorship, banking failure, and jurisdiction-specific regulation.
* **Return-free risk.** The issuer keeps the yield earned on the backing and passes the depeg risk to the holder. You take the downside; they take the income.

#### The decentralized attempts and their limits

Decentralized designs tried to remove that dependency, and historically ran into three walls:

* **Overcollateralized stablecoins** scaled only as fast as on-chain leverage demand for ETH, and several have since leaned on tokenized Treasuries to grow, trading away censorship resistance for scale.
* **Algorithmic stablecoins** proved structurally fragile and have repeatedly failed.
* **Prior delta-neutral synthetic dollars** could not scale because they depended on decentralized venues that, at the time, lacked the liquidity to absorb their hedges. When a protocol's own short positions overwhelmed a thin venue, funding rates turned against it and the model broke.

That last wall is the one most relevant to Synclear, and the one that has moved the most.

#### The landscape has shifted

The constraint that limited earlier on-chain delta-neutral designs was real, and it is now lifting quickly. Decentralized perpetual venues have gone from a niche to a structural part of the market:

* Perp DEX trading volume grew from $1.50 trillion in 2024 to $6.38 trillion in 2025, more than a fourfold increase in a single year.
* Decentralized venues now hold around 13.5% of perpetuals open interest, led by Hyperliquid, up from low single digits at the start of 2025.
* Hyperliquid alone carries roughly $10 billion in open interest, more than all other major perp DEXs combined.
* During the Q4 2025 drawdown, CEX spot volume collapsed from $2.21T to $0.95T while perp DEX volumes held strong, peaking at $1.18T in October, showing that on-chain derivatives liquidity is becoming resilient rather than fair-weather.

The trend is not a straight line. The DEX-to-CEX ratio has moved with normal volatility, and centralized venues still hold the majority of perpetual volume. But the two-year direction is unambiguous, and it points one way. A fully on-chain delta-neutral dollar no longer depends on liquidity that does not exist. It depends on liquidity that is growing every year, and protocols like Synclear that consistently supply the short side are part of what deepens it.

#### Learning from the leaders

Three protocols define the current synthetic-dollar landscape. Each pioneered something genuine, and each carries a structural limitation that comes from the choices it made.

**Ethena** proved the delta-neutral synthetic dollar at scale. It is the standard design for backing a dollar with hedged crypto rather than fiat reserves. Its constraint is where the hedging happens: Ethena executes on centralized exchanges through off-exchange custody, gates direct minting and redemption behind KYC for whitelisted market makers, and has faced regulatory friction (its token was barred in the EU under MiCA). The result is excellent scale built on a centralized operational perimeter.

**Sky** (formerly MakerDAO) proved the PSM and the overcollateralized CDP, and remains one of the largest and most battle-tested dollar systems in DeFi. Its constraints are yield and backing: the savings rate is set by governance vote rather than the market, and a large share of backing is USDC parked in the PSM and tokenized Treasuries, which means Sky's dollar inherits much of the same centralized exposure as the assets behind it, at a yield that has sat in the 3.5%-7% range.

**Falcon** advanced multi-asset collateral, accepting a broad basket from blue-chip crypto to tokenized real-world assets to mint its dollar. Its constraints are custody, capital inefficiency, and verifiability: a large majority of its reserves are held off-chain with centralized custodians, minting and redemption require KYC, and the protocol has drawn scrutiny over reserve transparency and has experienced depeg episodes. The collateral breadth is real but also poses the necessity of overcollateralization; the trust assumptions behind it are heavier than they first appear.

None of these are architecturally flawed. Their yield-bearing dollars are exactly the kind of productive collateral Synclear accepts in its Credit Markets, so their success expands Synclear's own collateral base. The point is not that they failed. It is that each made a centralizing trade to reach scale, and that trade leaves a clean space for a protocol that does not make it.

#### How Synclear compares

<table data-header-hidden><thead><tr><th></th><th width="128"></th><th width="147"></th><th></th><th></th></tr></thead><tbody><tr><td></td><td>Ethena</td><td>Sky</td><td>Falcon</td><td><strong>Synclear</strong></td></tr><tr><td>Backing model</td><td>Delta-neutral (CEX)</td><td>CDP + RWA/USDC</td><td>Multi-asset, overcollateralized</td><td><strong>Delta-neutral (DEX) + diversified, on-chain</strong></td></tr><tr><td>Custody</td><td>Off-exchange (centralized)</td><td>On-chain + RWA custodians</td><td>~Off-chain custodians</td><td><strong>Fully on-chain</strong></td></tr><tr><td>Hedging venues</td><td>Centralized exchanges</td><td>n/a</td><td>Centralized exchanges</td><td><strong>Decentralized exchanges</strong></td></tr><tr><td>Mint / redeem</td><td>KYC, whitelisted</td><td>Permissionless</td><td>KYC required</td><td><strong>Permissionless</strong></td></tr><tr><td>Yield source</td><td>Funding + staking</td><td>Governance-set rate</td><td>Custodial strategies</td><td><strong>Funding + on-chain credit + diversified</strong></td></tr><tr><td>Borrow against collateral</td><td>No</td><td>Yes (via Spark)</td><td>No</td><td><strong>Yes, with on-chain credit scoring</strong></td></tr><tr><td>Scale ceiling</td><td>Very high</td><td>Very high</td><td>High</td><td><strong>Grows with DEX open interest</strong></td></tr></tbody></table>

Synclear's position is the one none of the leaders occupy: a synthetic dollar whose backing, custody, and hedging are all on-chain and permissionless, paired with a credit market where users borrow against their assets on terms set by an on-chain credit score. The yield engine mints the dollar and funds the borrowing; the credit market creates demand for the dollar and a yield stream that does not depend on perpetual funding at all. Each layer scales on a different axis, so together they grow past the ceiling that limits a yield product alone.

#### The trade-offs we accept

Synclear states its trade-offs plainly rather than hiding them:

* **Scale grows with DeFi, not ahead of it.** A fully on-chain delta-neutral sleeve is bounded by decentralized open interest, so Synclear will not match the raw scale of a centralized-venue design on day one. The convert-to-stable design means supply is never capped by any single venue, and the addressable ceiling rises every year as on-chain markets deepen. Synclear is built to grow with that curve, and to help bend it.
* **On-chain execution carries oracle and venue risk.** Pricing and hedging on decentralized infrastructure means exposure to oracle failure and venue stress. Synclear mitigates this with multi-venue diversification, position limits, oracle redundancy, and circuit breakers, but the risk is real and disclosed.
* **The asset manager is a hybrid.** Cross-venue hedging cannot be executed purely on-chain, so an off-chain router proposes allocations inside an immutable on-chain envelope that holds custody and enforces every limit. The router can never move funds outside the rules or take custody. This is a deliberate, disclosed design, and it decentralizes progressively over time.

Full detail on every risk is in the [Risk Disclosure](https://claude.ai/risks-and-resources/diligence-materials/risk-disclosure.md).
