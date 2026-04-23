---
layout:
  width: wide
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
---

# Introductory Guides

{% tabs %}
{% tab title="User Guide (For Individuals)" %}
Tythe gives you a financial reputation that works for you. This guide walks you from zero footprint to active value: your profile set up and your live scores and limits working across every integrated market.

***

**What You're Building on Tythe**

Three primitives come together to make your Tythe profile work.

1. **Credit Profile (CEP)** Your sovereign financial identity. Anchored on the `did:cheqd` network, your Credit Profile links your verified identity, your wallets, your credentials, and your credit history into one portable, privacy-preserving profile. You own it permanently. No institution holds it for you.
2. **Tokenized Creditworthiness (TCT)** Your on-chain credit character score. A non-transferable token between 300 and 850, earned through seven behavioral inputs: historical performance, current risk exposure, credit utilization, new credit activity, volatility quotient, credit mix, and action integrity. TCT governs your terms on every integrated market.
3. **Maximum Vouchsafed Value (MVV)** Your credit limits, derived from your capital capacity. Two values:

* **tMVV (transaction limit):** The maximum value-based enhancement CAL can apply on any single transaction. A hard ceiling per transaction.
* **rMVV (rolling limit):** Your 30-day enhancement budget across all transactions. rMVV = tMVV x 10. Every value-based enhancement you receive depletes your rMVV. It resets automatically every 30 days.

Transactions above your limits still go through. The enhancement covers what fits within your limits. The remainder transacts at standard terms.

***

**Step 1. Create Your Credit Profile**

Go to the Tythe Dashboard and complete two steps:

1. **zk-KYC via Billions.** Identity verification and sanctions screening, processed entirely via zero-knowledge attestation. Tythe never holds your raw identity data at any point.
2. **Connect your primary wallet.** Bind a wallet address to your Credit Profile as your on-chain anchor.

Once both are done, your `did:cheqd` identifier is minted. Your Credit Profile is live and the scoring engine is active on your profile.

***

**Step 2. Build Your Profile**

Your Credit Profile pulls on-chain data from connected wallets automatically. The stronger your signal, the more accurately the protocol scores your TCT and sizes your MVV limits.

* **Link every active wallet.** A wallet you use on Morpho that is not linked to your Credit Profile is creditworthiness the protocol cannot see and cannot reward you for. CAL only applies enhancements to wallets linked to your Credit Profile. Unlinked addresses are treated as anonymous regardless of your actual scores. Link all active addresses once via the Dashboard.
* **Add Proof of Personhood.** Connect a World ID or equivalent biometric credential for a fixed **+5 TCT boost** and stronger Sybil resistance. Optional but recommended.
* **Log manual activity.** Use the Data tab to record financial activity the protocol cannot yet pull automatically, such as RWA positions on Centrifuge, Maple, Ondo, and other platforms not yet natively supported. Richer history means more accurate scoring across your Credit Mix and Action Integrity inputs.
* **zkTLS off-chain verifications** _(Coming post-launch):_ Once live, zkTLS will allow you to verify off-chain financial data (bank statements, income records, payroll, and more) directly to your Credit Profile without exposing the underlying documents. This expands your scoring surface beyond on-chain activity and strengthens your TCT and MVV for participants with strong off-chain financial histories.

***

**Step 3. Understand Your Score and Limits**

**TCT** is your character score. Behavioral inputs determine your bracket. Capital alone cannot move you into a higher bracket. Only behavior earns it.

| Range   | Bracket   | CAL Action                                                   |
| ------- | --------- | ------------------------------------------------------------ |
| 800–850 | Excellent | <mark style="color:$success;">Enhancement</mark> (High)      |
| 740–799 | Very Good | <mark style="color:$success;">Enhancement</mark> (Low)       |
| 670–739 | Good      | <mark style="color:$primary;">Risk Neutral</mark>; No Change |
| 580–669 | Fair      | <mark style="color:$warning;">Enforcement</mark> (Low)       |
| 300–579 | Poor      | <mark style="color:$warning;">Enforcement</mark> (High)      |
| 1       | No Data   | <mark style="color:$info;">Credit Invisible</mark>           |
| 0       | Flagged   | <mark style="color:$danger;">Blocked</mark>                  |

**tMVV and rMVV** are your credit limits, expressed as dollar amounts. tMVV caps any single value-based enhancement. rMVV is your 30-day budget: it depletes as value-based enhancements are applied and resets every 30 days. Neither is scored on a bracket. CAL reads them independently alongside your TCT bracket.

Your scores and limits exist in two states. Your **staged values** are computed continuously off-chain and are always current. Your **on-chain balances** are updated only when you Refresh. Integrated markets read your on-chain balances.

Full formula breakdown in the [TCE-26 Standard](../the-tythe-standard.md).

***

**Step 4. Refresh Your Score and Limits**

Refreshing mints your current staged values as your live on-chain balances. One transaction updates TCT, tMVV, and rMVV simultaneously.

Hit **Refresh** on the Dashboard before opening a new position, before a rate negotiation, or when Tythe notifies you of a meaningful score increase. Here is what happens:

1. The scoring engine computes current values for TCT, tMVV, and rMVV
2. A signed EIP-712 attestation is generated carrying all three values
3. The attestation is passed to your wallet for submission
4. You sign and submit. TCT, tMVV, and rMVV update on-chain atomically.

You pay the gas. No one else can refresh your scores on your behalf. Refresh at the right moment, not the most frequent one.

***

**Step 5. Put Your Score and Limits to Work**

With your on-chain values live, the Credit Adjustment Layer (CAL) applies automatically on every integrated market you interact with. It reads your TCT bracket, tMVV, and available rMVV at transaction time and applies the corresponding action instantly. No manual application, no approval process.

**CAL applies two independent adjustments:**

* **Value track:** Applies to dollar-denominated parameters such as collateral amounts, credit limits, and flat fees. Capped at the lowest of your tMVV, remaining rMVV, and the transaction value. Depletes your rMVV budget as enhancements are applied.
* **Rate track:** Applies to percentage-based parameters such as interest rates, LTV ratios, and margin requirements. Your TCT bracket alone governs this track. Does not deplete rMVV.

**By market type:**

* **Lending markets:** High-TCT borrowers access lower interest rates and reduced collateral requirements automatically.
* **Exchanges and derivatives:** High-TCT traders access tighter spreads and reduced margin requirements.
* **Insurance protocols:** High-TCT participants access lower premiums automatically.
* **Card issuers:** High-TCT cardholders access higher credit limits and better fee structures. tMVV governs the per-transaction enhancement ceiling.

Your creditworthiness follows your Credit Profile, not your geography. Any integrated market, anywhere.

***

**Step 6. Protecting Your Score**

**Auto-Slash is immediate and gasless.** A Liquidation, Default, or Exploit on any wallet linked to your Credit Profile triggers an instant TCT reduction with no warning and no delay. A sudden slash may trigger automated adjustments on your active positions across integrated markets. Maintain healthy collateral ratios and avoid edge behavior.

**Disputed slashes have a resolution path.** If you believe a slash was applied in error, raise a dispute with the Justice Arm of the Tythe DAO. AI clerks prepare an evidence brief from your on-chain data. A human jury drawn from your TCT band reviews the case and delivers a verdict. Available in V1.2.

**Protect your scores across wallet changes.** Your Credit Profile is anchored to your root `did:cheqd` identity, not a single wallet. Before rotating addresses, link your latest EIP-712 scoring attestation to your DID as a DID-Linked Resource. This preserves your scoring relationship across the change. If the attestation is not linked before you lose access to a wallet, your scores may not be recoverable.

***

**What's Coming**

1. **Tythe DAO and TYT Token** _(V1.2):_ TYT holders vote on protocol upgrades, fee parameters, and new feature proposals. The Justice Arm handles contested slashes and TCT disputes.
2. **Tythe Prime** _(V2):_ The capital efficiency space for Prime and Superprime borrowers. Your TCT and MVV unlock better rates and increased borrowing power on integrated lending markets.
3. **Credit Data Exchange** _(V3):_ Sell your verified credit data to institutional buyers for risk modeling, agent training, and credit event patterning. Your data, your revenue
{% endtab %}

{% tab title="Integration Guide (For Developers)" %}
Tythe gives your protocol verifiable, real-time credit intelligence at the smart contract level. This guide covers what Tythe exposes and which primitive solves which problem.

***

**What Tythe Exposes**

Four on-chain primitives and one off-chain intelligence feed. Integrate one or all. They are composable by design.

| Primitive            | What It Is                                                                     | What You Build With It                                |
| -------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------- |
| Credit Profile (CEP) | Sovereign DID on `did:cheqd` with verified KYC and wallet-to-identity mappings | Permissioned access, compliance gating                |
| TCT                  | Non-transferable ERC-20 credit score (300-850)                                 | Risk-adjusted rates, dynamic LTV, credit-aware vaults |
| tMVV + rMVV          | Per-transaction credit ceiling and 30-day rolling enhancement budget           | Enhancement limits, credit capacity bounds            |
| CAL                  | Smart contract primitive applying TCT-based adjustments at transaction time    | Automated credit-differentiated execution             |
| Relay Emitter        | Off-chain ML-powered nEvent feed with real-time labels and percentile rankings | Live risk monitoring, default detection               |

***

**1. Credit Profile (Identity Resolution)**

Call `resolveWallet(address wallet)` on the Attestation Registry. Returns the wallet's associated `did:cheqd` identifier and primary wallet address. Returns `("", address(0))` for any unlinked wallet. Treat unlinked wallets as anonymous.

What resolution confirms:

* Verified KYC and sanctions status via zero-knowledge attestation
* Proof of Personhood confirmed human uniqueness
* Wallet-to-identity binding. Every linked address maps to one verified root DID.

**Build to the DID, not the wallet address.** A participant's Credit Profile persists across wallet rotations. The DID is the persistent identifier for a participant's credit state. No raw PII ever touches your protocol.

```solidity
isLinked(address wallet)    // true if wallet has a linked Credit Profile
```

> **Use when:** Your protocol needs to verify a participant is a real, KYC-compliant individual before granting access to lending markets, permissioned vaults, insurance pools, or card products.

***

**2. TCT, tMVV, rMVV (Credit Signals)**

All signals are readable from the TCT Contract. One contract address, one integration.

```solidity
balanceOf(address wallet)              // TCT score (300-850)
getTMVV(address wallet)                // tMVV in USD, 18 decimals
getAvailableRMVV(address wallet)       // remaining rMVV in current 30-day window
getScoreBracket(address wallet)        // Bracket enum
scoreToBracket(uint256 score)          // convert raw score to Bracket enum
isEligible(address, uint256 minTCT)    // true if TCT >= minTCT
isBlacklisted(address)                 // true if wallet is blacklisted
```

**Score brackets:**

| Range   | Bracket   | CAL Action         |
| ------- | --------- | ------------------ |
| 800-850 | Excellent | Enhancement (High) |
| 740-799 | Very Good | Enhancement (Low)  |
| 670-739 | Good      | Neutral            |
| 580-669 | Fair      | Enforcement (Low)  |
| 300-579 | Poor      | Enforcement (High) |
| 1       | No Data   | Credit Invisible   |
| 0       | Flagged   | Blocked            |

**tMVV and rMVV are dollar ceilings, not bracket scores.**

* tMVV caps the value-based enhancement on any single transaction.
* rMVV is the 30-day rolling budget. Every value-based enhancement depletes rMVV by the enhancement amount. When rMVV hits zero, no further value-based enhancements until the window resets. Rate-based adjustments never deplete rMVV.
* CAL's effective value-based enhancement ceiling per transaction = `min(tMVV, availableRMVV, transactionValue)`.

**Read at transaction time, not session initiation.** TCT updates between transactions via Manual Refresh (positive) or Auto-Slash (negative). rMVV depletes in real time. A cached value is stale the moment anything changes.

> **Use when:** Your protocol needs differentiated risk pricing: dynamic LTV, risk-adjusted interest rates, tiered margin requirements, or credit-aware insurance premiums.

***

**3. CAL (Credit Adjustment Layer)**

CAL is a smart contract primitive that any protocol builds into their transaction flow for automatic, credit-differentiated adjustments based on a borrower's TCT score. Three integration paths are available.

**Path 1: Native integration** For protocols building with CAL pre-launch or rebuilding before their next major version. Inherit CAL, override `_executeWithCredit()`, and get fully automated credit-differentiated execution baked into your transaction flow.

**Path 2: Advisory integration** For existing protocols that cannot or choose not to rebuild. Call `getCreditAction(address wallet, uint256 transactionValue, address market)` as a public view function at transaction time. Receive a `CreditAction` struct. Implement the adjustment in your own execution logic. One external call. No rebuilding required.

**Path 3: Direct read** Read TCT and MVV directly from the TCT contract and build entirely custom adjustment logic. No CAL interaction required.

**Register your market:**

Call `registerMarket(address market, MarketConfig calldata config)`.

One immutable flag set at registration determines the integration pathway:

* `isInternal = true`: Tythe Prime. Value track is MVV-governed, capped at `min(transactionValue, tMVV, availableRMVV)` and depletes rMVV on every Enhancement.
* `isInternal = false`: External protocol. Value track is uncapped. No rMVV consumption.

**MarketConfig struct:**

solidity

```solidity
struct MarketConfig {
    bool    isActive;
    bool    isInternal;                  // immutable after registration

    // Value track — MVV-governed on internal, uncapped on external
    // Apply to dollar-denominated parameters (collateral amounts, credit limits, flat fees)
    uint256 excellentValueFloorBps;      // adjustment at TCT 800
    uint256 excellentValueCeilBps;       // adjustment at TCT 850, DAO ceiling 1000 (10%)
    uint256 veryGoodValueFloorBps;       // adjustment at TCT 740
    uint256 veryGoodValueCeilBps;        // adjustment at TCT 799, DAO ceiling 500 (5%)
    uint256 fairValueFloorBps;           // adjustment at TCT 580
    uint256 fairValueCeilBps;            // adjustment at TCT 669, DAO ceiling 750 (7.5%)
    uint256 poorValueFloorBps;           // adjustment at TCT 300
    uint256 poorValueCeilBps;            // adjustment at TCT 579, DAO ceiling 1500 (15%)

    // Rate track — unconstrained on both pathways, no MVV cap
    // Apply to percentage-based parameters (interest rates, LTV ratios, margin requirements, percentage fees)
    uint256 excellentRateFloorBps;       // adjustment at TCT 800
    uint256 excellentRateCeilBps;        // adjustment at TCT 850, DAO ceiling 300 (3%)
    uint256 veryGoodRateFloorBps;        // adjustment at TCT 740
    uint256 veryGoodRateCeilBps;         // adjustment at TCT 799, DAO ceiling 150 (1.5%)
    uint256 fairRateFloorBps;            // adjustment at TCT 580
    uint256 fairRateCeilBps;             // adjustment at TCT 669, DAO ceiling 225 (2.25%)
    uint256 poorRateFloorBps;            // adjustment at TCT 300
    uint256 poorRateCeilBps;             // adjustment at TCT 579, DAO ceiling 450 (4.5%)

    address feeToken;
}
```

**Linear interpolation:** For every non-neutral bracket, you configure a floor bps (adjustment at bracket minimum score) and a ceiling bps (adjustment at bracket maximum score). Every score in between is interpolated linearly. Floor bps are uncapped. Ceiling bps cannot exceed the DAO maximum.

```
adjustment = floorBps + ((ceilBps - floorBps) x (score - bracketFloor)) / (bracketCeiling - bracketFloor)
```

Example: Excellent value track configured at floorBps = 300, ceilBps = 1000:

* TCT 800 = 3% adjustment
* TCT 825 = 6.5% adjustment
* TCT 850 = 10% adjustment

**CreditAction struct:**

```solidity
struct CreditAction {
    ActionType valueAction;      // action type for the MVV-governed track
    uint256    valueMagnitude;   // final bps after interpolation and consumption modifier
    uint256    effectiveCeiling; // internal: min(txValue, tMVV, availableRMVV) | external: 0
    ActionType rateAction;       // action type for the unconstrained track
    uint256    rateMagnitude;    // final bps after interpolation, never MVV-governed
}
```

**ActionType enum:**

```solidity
enum ActionType {
    HighBoost,     // Excellent
    LowBoost,      // Very Good
    Neutral,       // Good, NoData (external), exhausted rMVV on value track
    LowReduction,  // Fair
    HighReduction, // Poor
    Block          // Slashed — always, no override
}
```

**On Block:** CAL reverts with `BlockedWallet()` directly. No handling required by your protocol.

**On Enhancement (internal pathway only):** CAL automatically calls `consumeRMVV` on the TCT contract after applying a value-based Enhancement. Your protocol does not need to handle rMVV depletion.

**isInternal is immutable.** Attempting to change it via `updateMarketConfig` reverts with `CannotChangePathway()`.

**Fee model:**

* Enhancement: 0.07% collected on-chain from the borrower wallet at transaction time when feesActive. Off by default.
* Enforcement: Counter increments on every LowReduction or HighReduction. Billed off-chain monthly.
* Block: Free. No fee, no counter.

> **Use when:** Your protocol wants automated, credit-differentiated execution. For lending markets, derivatives and exchanges, insurance protocols, and card issuers.

***

**4. Relay Emitter**

Off-chain intelligence feed. Subscribe via the Tythe Developer Portal. Labels and percentile rankings delivered to your systems in real time.

**nEvent types:**

| Event       | Trigger                                 | Enforcement                             |
| ----------- | --------------------------------------- | --------------------------------------- |
| Liquidation | Collateral failure on integrated market | Auto-Slash, severity by percentile rank |
| Default     | Loan not repaid within grace period     | Auto-Slash, severity by percentile rank |
| Exploit     | Verified protocol attack involvement    | Blacklist, CEP revoked, TCT set to zero |
| Mercenary   | Rapid liquidity withdrawal under stress | Alert only                              |
| Informed    | Patterned high-alpha toxic flow         | Alert only                              |
| Whale       | Objectively large on-chain transaction  | Alert only                              |

Each label includes CEP ID, event typology, percentile rank within the label spectrum, TCT delta where applicable, and epoch timestamp for replay prevention.

> **Use when:** Your protocol needs early warning on counterparty credit deterioration. For lending markets, vault managers, derivatives and exchanges, RWA platforms, and institutional risk desks.

***

**Composable Stacks**

| Use Case                    | Primitives                                  |
| --------------------------- | ------------------------------------------- |
| Credit-aware lending market | CEP + TCT + tMVV/rMVV + CAL                 |
| Risk-managed vault          | TCT + tMVV/rMVV + Relay Emitter             |
| Card issuer                 | CEP + TCT + tMVV/rMVV + CAL                 |
| Institutional risk desk     | Relay Emitter + TCT + tMVV/rMVV             |
| Full-stack integration      | CEP + TCT + tMVV/rMVV + CAL + Relay Emitter |

***

**What's Coming**

**APIs and SDKs** _(Roadmap):_ REST APIs and language-specific SDKs for web2-native integration. Contact [dev@tythe.network](mailto:dev@tythe.network) if your stack requires API access ahead of the roadmap.

**Tythe DAO and TYT Token** _(V1.2):_ Vote on technical specifications, integration standards, and protocol upgrade paths.

**Tythe Prime** _(V2):_ Integration hooks for protocols connecting to Tythe Prime vaults.

**Credit Data Exchange** _(V3):_ Anonymized, user-consented credit data for model building and risk research.

**Agentic Credit** _(V3):_ AI agents access credit through the same primitives. No additional integration required.
{% endtab %}

{% tab title="Business Guide (For Institutions)" %}
Anonymous counterparties are your most expensive problem. Every position you size, every rate you set, every trade you clear, you are pricing in risk you cannot measure. Tythe gives you the infrastructure to measure it.

***

**What Tythe Gives You**

Four on-chain primitives and one off-chain intelligence feed. Each addresses a specific capital efficiency or risk management problem.

<table><thead><tr><th width="175">Primitive</th><th>What It Is</th><th>The Problem It Solves</th></tr></thead><tbody><tr><td>Credit Profile (CEP)</td><td>Sovereign DID on <code>did:cheqd</code>. Resolves a complete financial profile without exposing raw data.</td><td>Anonymous counterparties. Compliance overhead.</td></tr><tr><td>TCT</td><td>Non-transferable borrower character score (300-850). Primary signal for lending, exchanges, insurance, and card markets.</td><td>Undifferentiated risk pricing. Every participant treated as anonymous worst-case.</td></tr><tr><td>tMVV + rMVV</td><td>Per-transaction credit ceiling and 30-day rolling enhancement budget. Sized by verified capital capacity.</td><td>Enhancement without accountability. Credit limits that do not reflect actual capital.</td></tr><tr><td>CAL</td><td>Smart contract primitive applying TCT-based adjustments at transaction time. Two independent tracks: value and rate.</td><td>Manual underwriting. Static rate structures. Reactive enforcement.</td></tr><tr><td>Relay Emitter</td><td>Off-chain ML-powered nEvent feed with real-time labels and percentile rankings.</td><td>Delayed default detection. Reactive risk management.</td></tr></tbody></table>

***

**The Capital Efficiency Case**

Every market today prices anonymous participants at the same worst-case rate. That is capital inefficiency by design. You leave revenue on the table from high-quality participants and absorb unnecessary risk from low-quality ones.

Tythe makes the distinction machine-readable, on-chain, and enforceable at the contract level. A participant with an Excellent TCT score is not the same borrower as someone with no credit history. A participant with a high tMVV is not the same capital capacity as one with a near-zero credit limit.

High-reliability participants get better terms: your protocol becomes more competitive. Low-reliability participants face tighter controls: your default and liquidation exposure decreases. Both happen automatically, without manual underwriting, at the point of every transaction.

***

**The Compliance Case**

Verifying users today means handling raw PII, maintaining KYC infrastructure, and accepting ongoing data liability. Most protocols skip it entirely or expose themselves trying.

Credit Profile integrates zk-KYC and privacy-preserving sanctions screening via Billions. Identity verification and OFAC/AML screening are processed entirely via zero-knowledge attestation. Your market receives a cryptographic pass/fail signal, never the underlying personal data. No KYC stack to build. No data liability to absorb. Compliance handled at the identity layer before a participant ever reaches your market.

***

**The Risk Management Case**

By the time most protocols detect credit deterioration, the damage is done. The Relay Emitter changes the timeline.

The moment a Liquidation, Default, Exploit, or Mercenary event is detected, a structured label reaches your risk systems in real time before contagion spreads. Every label includes the CEP ID, event typology, severity percentile rank, TCT delta, and epoch timestamp. For institutions managing active exposure across multiple markets, receiving a Default signal at detection rather than after the fact is the difference between proactive and reactive risk management.

***

**Use Cases by Institution Type**

**DeFi Lending:** CAL reads TCT and applies two independent adjustments: value-based collateral reductions and rate-based interest discounts for high-reliability borrowers. Low-reliability positions face tighter terms automatically. tMVV and rMVV ensure enhancements are always sized to verified capital capacity. No manual intervention required. Relay Emitter surfaces Liquidation and Default events before they affect your book.

**Derivatives and Exchanges:** Differentiated fee structures, spreads, and margin requirements based on live TCT. High-TCT traders access better execution on both tracks. Counterparty risk priced accurately at the point of every trade. Informed trading flagged by the Relay Emitter before it reaches your liquidity.

**DeFi Insurance:** Dynamic premiums applied at entry based on TCT. Reliable participants access lower premiums automatically. Pool solvency improves without manual underwriting. Exploit events surfaced by the Relay Emitter before they affect your coverage pool.

**Card Issuers:** TCT and tMVV provide the on-chain credit signal for dynamic credit limit assignment and spending controls. High-reliability cardholders access higher limits and better fee structures automatically. tMVV sets the per-transaction enhancement ceiling. rMVV ensures the 30-day enhancement budget reflects actual capital capacity. Credit Profile compliance verification satisfies KYC requirements at onboarding without handling raw cardholder data.

***

**Recommended Integration Stack**

<table><thead><tr><th>Institution</th><th>CEP</th><th>Signal</th><th width="141">CAL</th><th>Relay Emitter</th></tr></thead><tbody><tr><td>DeFi Lending</td><td>Yes</td><td>TCT + tMVV/rMVV</td><td>Yes</td><td>Yes</td></tr><tr><td>Derivatives and Exchanges</td><td>Yes</td><td>TCT + tMVV/rMVV</td><td>Yes</td><td>Yes</td></tr><tr><td>DeFi Insurance</td><td>Yes</td><td>TCT + tMVV/rMVV</td><td>Yes</td><td>Yes</td></tr><tr><td>Card Issuers</td><td>Yes</td><td>TCT + tMVV/rMVV</td><td>Yes</td><td>Recommended</td></tr></tbody></table>

***

**What's Coming**

**APIs and SDKs** _(Roadmap):_ REST APIs and SDKs for web2-native integration. Contact [business@tythe.network](mailto:business@tythe.network) for API access ahead of the roadmap.

**Tythe DAO and TYT Token** _(V1.2):_ Institutional DAO members vote on scoring formula parameters and protocol upgrades. Institutional members are the only participants with visibility into exact formula weights.

**Tythe Prime** _(V2):_ The capital efficiency space for Prime and Superprime borrowers. Institutions deploying capital as vault LPs access credit-differentiated borrower pools backed by Tythe's scoring infrastructure.

**Credit Data Exchange** _(V3):_ Anonymized, user-consented credit data in structured formats for risk modeling, research, and AI training.

**Agentic Credit** _(V3):_ High-reputation AI agents with verified execution history access credit through the same stack. Institutions integrated today automatically serve a new class of creditworthy counterparty. No additional integration required.
{% endtab %}
{% endtabs %}
