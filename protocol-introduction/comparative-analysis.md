# Comparative Analysis

On-chain dollar finance is no longer early. There are live protocols managing billions, and there is a decade of precedent that shows which designs endure and which fail. This page places Synclear inside that record with data. It gives credit where competitors have earned it, and it is specific about the axes where Synclear is built differently and why that matters.

#### The landscape

The protocols nearest to Synclear cluster into three groups: synthetic-dollar yield (Ethena, Falcon), tokenized real-world assets and curated savings (Ondo, Sky), and on-chain credit (Maple, and the failed Goldfinch). The table below is a factual snapshot, not a ranking. Figures are drawn from public dashboards in Q2 2026 and move continuously.

| Protocol     | Model                                               | Scale (2026)       | Yield                       | Backing / collateral                                                             | Originates credit           |
| ------------ | --------------------------------------------------- | ------------------ | --------------------------- | -------------------------------------------------------------------------------- | --------------------------- |
| **Ethena**   | Synthetic dollar, single delta-neutral basis trade  | \~$5.6–5.9B USDe   | sUSDe \~9–12% (range 4–35%) | Staked ETH and BTC, hedged with short perps                                      | No                          |
| **Falcon**   | Overcollateralized synthetic dollar, multi-strategy | \~$1.3–1.5B TVL    | sUSDf \~8.7%                | Wide: BTC, ETH, SOL, altcoins, stablecoins, RWAs                                 | No                          |
| **Sky**      | Curated savings, stablecoin                         | Multi-billion USDS | sUSDS 3.75%                 | Tokenized RWAs and overcollateralized crypto lending                             | No                          |
| **Ondo**     | Tokenized US Treasuries                             | \~$3.5–3.8B TVL    | Tracks T-bill rate          | US Treasuries, held with institutional custodians                                | No                          |
| **Maple**    | Institutional crypto lending                        | \~$2.1–3.9B TVL    | High single digits          | Overcollateralized crypto (105–150%+), some institutional undercollateralized    | Yes, to trading firms       |
| **Synclear** | Asset manager and credit originator                 | Launch             | Tiered by product           | Conservative tiered: T-bills, lending, cash, plus a bounded delta-neutral sleeve | Yes, to on-chain businesses |

Two honest observations from this table. First, Synclear enters with a design, not a track record, and the incumbents have real scale. Second, of every protocol here, only Maple originates credit, and it lends to crypto trading firms, not to operating businesses. The rest assemble yield from existing sources. That gap is where Synclear is built to be different.

#### Where Synclear is built differently

**1. You choose your risk. You are not pooled into one.**

Ethena and Falcon each issue a single dollar backed by a single pooled strategy set. When you hold USDe or USDf, you hold that protocol's entire risk posture, whatever it happens to be. With Ethena, that means exposure to perpetual funding rates, which is why sUSDe yield has ranged from 4% to 35% and can compress toward zero when funding turns negative, as it did in the October 2025 unwind that took USDe supply from roughly $14B down to under $6B. With Falcon, it means backing that includes a wide set of assets: alongside BTC, ETH, and stablecoins, Falcon accepts long-tail tokens such as SOL, AVAX, NEAR, and TON as collateral. Falcon manages this with overcollateralization and an insurance fund, and it is a legitimate design, but every USDf holder shares that collateral base whether they would choose it or not.

Synclear does not pool everyone into one dollar. Each product carries its own backing and its own risk, and the user selects the tier: Open Savings holds only treasury bills, on-chain lending, and cash; Gated Savings adds a delta-neutral sleeve capped at roughly 10 to 20 percent; the funds take defined strategy risk for those who opt in. Reaching for more yield is a choice the user makes, not a property of a single token they must hold to participate. This is the difference between an asset manager and a single-strategy issuer.

**2. Diversified yield, including a source uncorrelated with crypto**

Ethena's yield comes from one place: perpetual funding. That is an elegant engine, and in positive-funding regimes it pays well, but it rises and falls with crypto market sentiment, and its worst periods coincide with everyone else's. Falcon diversifies across funding, spreads, staking, and options, which is genuinely more robust.

Synclear diversifies further, and adds a source none of the synthetic-dollar protocols hold: credit. Interest from lending to real businesses is driven by those businesses' economics, not by perpetual funding rates, so it does not move in lockstep with crypto sentiment. Combined with treasury-bill yield, on-chain lending, the delta-neutral sleeve, and the options book, this gives Synclear a yield base that draws from several independent regimes rather than one. Where a strategy is already run best by someone else, Synclear allocates to it rather than rebuilding it: the delta-neutral exposure routes to Ethena and Theo. The ecosystem is treated as a set of suppliers, not competitors.

**3. Credit origination, and done differently from those who tried it**

This is the axis that separates Synclear from the entire synthetic-dollar field, none of which originates credit, and from the two protocols that did.

**Against Maple.** Maple is the most successful on-chain credit protocol, near $2.1–3.9B in TVL and the category leader, rebuilt with real discipline after its 2022 failure. Credit is due there. But Maple lends to crypto-native trading firms for basis trades and inventory, secured either by overcollateralized crypto or, for vetted institutions, by underwriting and legal agreements. When one of those borrowers fails, recovery runs off-chain: as one risk report puts it plainly, there is nothing to seize on-chain, and lenders wait months or years for lawyers. Synclear lends to operating businesses against their on-chain revenue, and repayment runs through automated capture at the source of that revenue. Recovery is mechanical and continuous, not a lawsuit after the fact.

**Against Goldfinch.** Goldfinch is the cautionary tale, and it is a recent one: after roughly $100M originated over six years and a string of defaults, Tugende, Stratos, Lend East, it began winding down in June 2026, with at least one large depositor reporting recovery of only about 30 percent of principal. Its model was to lend to off-chain businesses in emerging markets, where, in the words of one critic, the borrower could literally flee and there were no credit bureaus and no practical legal recovery. The lesson its own founder drew was blunt: putting emerging-market credit on-chain does not make underwriting it any easier. Synclear inverts the part that killed Goldfinch. It lends only where revenue is already on-chain and can be captured at the source, so repayment does not depend on off-chain collection or a borrower's willingness to pay. The borrower cannot divert revenue the protocol is already capturing.

#### Lessons from the failures

The largest collapses in this category trace to a few root causes. Synclear rules out each by structure.

**Reflexive dollars (Terra, 2022).** UST was backed by its own sister token rather than by real assets. When confidence fell, backing and dollar fell together, and roughly $40B evaporated in days. Synclear holds real, dollar-stable assets, verifiable on-chain, and no product depends on the price of a Synclear-issued token to stay whole.

**Unsecured, concentrated credit (Maple v1, 2022).** When Orthogonal Trading concealed its FTX exposure and defaulted, it took $36M across eight loans, about 30 percent of Maple's active loans at the time, and the main pool lost 80 percent of remaining capital because it had lent most of its funds to that single borrower. Synclear isolates every borrower in its own market, so one default cannot spread, underwrites on live cash-flow data rather than trust, and captures revenue at the source rather than relying on the borrower to repay.

**Credit that cannot be enforced on-chain (Goldfinch, wound down 2026).** Off-chain borrowers, off-chain collection, no enforceable recovery. Synclear captures on-chain revenue directly, so repayment is mechanical rather than dependent on a promise or a courtroom.

#### Where this leaves Synclear

Synclear enters a proven category against real incumbents, and it does not claim their scale. What it claims is a design that combines what the survivors got right and avoids what the failures got wrong: an asset manager that lets each user choose their own risk rather than pooling everyone into one dollar, a yield base diversified across independent sources including credit, and a credit book that originates against on-chain revenue captured at the source, the one thing the synthetic-dollar field does not do and the two credit protocols that tried it could not do safely. The numbers above belong to the incumbents today. The design is Synclear's argument for why it belongs among them.

***

