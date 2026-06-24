# Comparative Analysis

Synclear did not invent the synthetic dollar. It builds on a lineage of protocols that each solved part of the problem, and it is designed to occupy the space they left open: a fully on-chain, permissionless dollar that scales with decentralized markets rather than depending on centralized ones.

#### Why stablecoins matter

Stablecoins are the most-used instrument in crypto. The large majority of trading pairs across spot and derivatives venues are denominated in them, they settle trillions of dollars on-chain, and they are the only crypto asset to have found durable, global product-market fit with over 100 million users. They are the foundation the rest of the industry is built on, and the largest single market crypto addresses.

That foundation still has structural gaps. To see where, it helps to separate two things that are often confused: what backs a dollar, and how centralized the system that runs it is.

**Backing model** is what stands behind the dollar: fiat reserves, overcollateralized crypto, an algorithm, or delta neutral hedged (a synthetic dollar). **Operational centralization** is a separate axis entirely: who custodies the assets, where execution happens, whether minting is permissioned, and whether the system can be censored. A dollar can be synthetic in its backing yet fully centralized in its operation. Most of today's leaders are exactly that. Synclear is built to minimize centralization on both axes at once: decentralized by default, with the centralization that remains kept bounded, disclosed, and used only as a backstop, where the leaders rely on it as their primary operating mode.&#x20;

#### Backing models and their limits

Each backing model solved part of the problem and left part open:

* **Fiat-backed** (USDC, USDT, USD1) is stable and capital-efficient, but the backing sits in bonds and regulated bank accounts, exposed to censorship, banking failure, and jurisdiction-specific regulation. It also carries return-free risk: the issuer keeps the yield earned on the backing and passes depeg risk to the holder. You take the downside; they take the income.
* **Overcollateralized crypto** scaled only as fast as on-chain leverage demand for ETH, and several such stablecoins have since leaned on tokenized treasuries to grow, trading away censorship resistance for scale.
* **Algorithmic** designs proved structurally fragile and have repeatedly failed.
* **Delta-neutral synthetic** dollars back the dollar with hedged crypto and are the most promising of the four. Earlier on-chain attempts could not scale because they depended on decentralized venues that, at the time, lacked the liquidity to absorb their hedges. When a protocol's own unbounded short positions overwhelmed a thin venue, funding rates turned against it and the model broke.

That last wall is the one most relevant to Synclear, and the one that has moved the most.

#### The centralization most leaders accept

The synthetic-dollar model itself does not require centralization, but reaching scale on it, so far, has. The leading synthetic dollars hedge on centralized exchanges, hold backing with off-chain custodians, and gate minting behind KYC. They are decentralized in marketing and centralized in operation. That is the trade each made to grow, and it is the gap Synclear is designed to fill: keeping backing, custody, and hedging on-chain and permissionless by default, while still capturing the same hedged-crypto yield. Synclear is not centralization-free, and does not claim to be. It holds stablecoins and tokenized treasuries a backstop and a baseline yield source, and it runs a hybrid execution router (described in the trade-offs below). The difference is one of degree and role: for the leaders, centralized custody and execution are the primary operating mode; for Synclear, the centralization that remains is minimal, bounded by hard on-chain limits, and used as a backstop rather than the foundation.

#### The landscape has shifted

The constraint that limited earlier on-chain delta-neutral designs was real, and it is now lifting quickly. Decentralized perpetual venues have gone from a niche to a structural part of the market:

* Perp DEX trading volume grew from $1.50 trillion in 2024 to $6.38 trillion in 2025, more than a fourfold increase in a single year.
* Decentralized venues now hold around 13.5% of perpetuals open interest, up from low single digits at the start of 2025, and the share runs higher in bull markets when on-chain leverage demand peaks.
* Liquidity is no longer concentrated in one venue. Hyperliquid still carries the largest share (roughly $10 billion in open interest), with Aster, Lighter, and Drift now holding significant share as well, giving a delta-neutral protocol several deep venues to hedge across rather than one. Single-collateral venues such as dYdX V4 and EdgeX add to overall on-chain open interest, and as they ship unified margin they expand the set further.
* During the Q4 2025 drawdown, CEX spot volume fell sharply while perp DEX volumes held strong, peaking near $1.4 trillion in October, showing that on-chain derivatives liquidity is becoming resilient rather than fair-weather.

The trend is not a straight line. The DEX-to-CEX ratio has moved with normal volatility, and centralized venues still hold the majority of perpetual volume. But the two-year direction is unambiguous, and it points one way. A fully on-chain delta-neutral dollar no longer depends on liquidity that does not exist. It depends on liquidity that is growing every year, and protocols like Synclear that consistently supply the short side are part of what deepens it.

#### Learning from the leaders

Three protocols define the current crypto/tokenized asset-backed dollar landscape. Each pioneered something genuine, and each carries a structural limitation that comes from the choices it made.

**Ethena** proved the delta-neutral synthetic dollar at scale. It is the standard design for backing a dollar with hedged crypto rather than fiat reserves. Its constraint is where the hedging happens: Ethena executes on centralized exchanges through off-exchange custody, and gates direct minting and redemption behind KYB/KYC for whitelisted institutions, hedge funds, and market makers. The result is excellent scale built on a centralized operational perimeter.

**Sky** (formerly MakerDAO) proved the PSM and the overcollateralized CDP, and remains one of the largest and most battle-tested dollar systems in DeFi. It is the one leader that is genuinely decentralized in operation: on-chain governance, permissionless CDPs, no custodian. Its trade is on the other axis. A large share of backing is now USDC parked in the PSM and tokenized treasuries, so the dollar is decentralized in machinery but increasingly centralized in what stands behind it, at a governance-set yield that has sat in the 3.5% to 7% range rather than a market rate.

**Falcon** advanced multi-asset collateral, accepting a broad basket from blue-chip crypto and tokenized real-world assets to governance tokens to mint its dollar. Its constraints are custody, capital inefficiency, and verifiability: a large majority of its reserves are held off-chain with centralized custodians, minting and redemption require KYC, and the protocol has drawn scrutiny over reserve transparency and has experienced depeg episodes. The collateral breadth is real, but it requires overcollateralization, and the trust assumptions behind it are heavier than they first appear.

None of these are architecturally flawed. Their yield-bearing dollars are exactly the kind of productive collateral Synclear accepts in its Credit Markets, so their success expands Synclear's own collateral base. The point is not that they failed. It is that each accepted centralization on at least one axis to reach scale: Ethena and Falcon in their operation, Sky in its backing. That leaves a clean space for a protocol that accepts it on neither.

#### How Synclear compares

Synclear's position is the one none of the leaders occupy: a synthetic dollar whose backing, custody, and hedging are on-chain and permissionless by default, paired with a credit market where users borrow against their assets on terms set by an on-chain credit score. The yield engine mints the dollar and funds the borrowing; the credit market creates demand for the dollar and a yield stream that does not depend on perpetual funding at all. Each layer scales on a different axis, so together they grow past the ceiling that limits a yield product alone.

The delta-neutral difference goes deeper than where the hedging happens. Synclear is designed so the constraint that broke earlier on-chain attempts cannot break it. The protocol caps its hedging at a conservative share of available open interest (7%), and when a venue cannot absorb more, new backing is converted to liquid stablecoins instead of forced onto the market. It never drives funding against itself to grow. Supply is therefore bounded by the depth of stable backing across DeFi, which is effectively unlimited, not by the open interest of any single venue, which is what killed prior delta-neutral dollars. The hedging sleeve scales with decentralized open interest as it grows, rather than breaking on it.

That same scarcity becomes a product rather than a ceiling. Because on-chain hedging capacity is genuinely limited, Synclear allocates it as a competitive, concentrated yield market rather than a benefit spread thin across everyone, turning the one hard constraint of on-chain delta-neutral into a source of yield in its own right. To learn more about Synclear's competitive delta-neutral hedging strategy, see [Yield & Asset Management](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/14/yield-and-asset-management).

#### The trade-offs we accept

Synclear states its trade-offs plainly rather than hiding them:

* **Scale grows with DeFi, not ahead of it.** A fully on-chain delta-neutral sleeve is bounded by Perpetual DEX open interest (OI), so Synclear will not match the raw scale of a centralized-venue design on day one. The convert-to-stable design means supply is never capped by any single venue, and the addressable ceiling rises every year as on-chain markets deepen. Synclear is built to grow with that curve, and to help bend it.
* **On-chain execution carries oracle and venue risk.** Pricing and hedging on decentralized infrastructure means exposure to oracle failure and venue stress. Synclear mitigates this with multi-venue diversification, position limits, oracle redundancy, and circuit breakers, but the risk is real and disclosed.
* **The asset manager is a hybrid.** Cross-venue hedging cannot be executed purely on-chain, so an off-chain router proposes allocations inside an immutable on-chain envelope that enforces every limit. The router can never move funds outside the rules or take custody. This is a deliberate, disclosed design, and it decentralizes progressively over time.

Full detail on every carried risk can be found on the [Risk Disclosure](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/10/risk-disclosure) page.
