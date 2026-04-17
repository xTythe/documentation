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
{% tab title="Individuals" %}
Tythe gives you a financial reputation that works for you. This guide walks you from zero footprint to active value; your profile set up, your live score, and your creditworthiness working across every integrated market.

***

**What You're Building**

Three things come together to make your Tythe profile work.

1. **Credit Enhancement Profile (CEP):** Your sovereign financial identity. Anchored on the `did:cheqd` network, your CEP links your verified identity, your wallets, your credentials, and your credit history into one portable, privacy-preserving profile. You own it permanently. No institution holds it for you.
2. **Tokenized Creditworthiness (TCT):** Your on-chain credit score. A non-transferable token between 300 and 850, earned through your on-chain behavior and tokenized on-chain when you choose. The higher your TCT, the better the capital terms available to you across every integrated market.
3. **Maximum Vouchsafed Value (MVV):** Your per-transaction enhancement ceiling, embedded in your TCT token alongside your score. When you interact with a CEW-integrated market, enhancements apply up to your MVV. Transactions above your MVV still go through. The enhancement is applied to the MVV portion, the remainder transacts at standard terms. MVV is derived from your Capital Capacity. Refresh to update it on-chain.

***

**Step 1. Create Your CEP**

Go to the Tythe Dashboard and complete two steps:

1. **zk-KYC via Billions:** Identity verification and sanctions screening, processed entirely via zero-knowledge attestation. Tythe never holds your raw identity data at any point.
2. **Connect your primary wallet:** Bind a wallet address to your CEP as your on-chain anchor.

Once both are done, your `did:cheqd` identifier is minted. Your CEP is live and the scoring engine is active on your profile.

***

**Step 2. Build Your Profile**

Your CEP pulls on-chain data from connected wallets automatically. The stronger your signal, the more accurately the protocol scores you.

**Link every active wallet:** A wallet you use on Morpho that isn't linked to your CEP is creditworthiness the protocol cannot see and cannot reward you for. CEW only applies enhancements to wallets linked to your CEP. Unlinked addresses are treated as anonymous regardless of your actual score. Link all active addresses once via the Dashboard.

**Add Proof of Personhood:** Connect a World ID or equivalent biometric credential for a fixed _+5 TCT boost_ and stronger Sybil resistance. Optional but recommended.

**Log manual activity:** Use the Data tab in the dashboard to record financial activity the protocol cannot yet pull automatically (RWA positions on Centrifuge, Maple, Ondo, and other platforms not yet natively supported). Richer history means more accurate scoring across your Investor Status, Credit Mix, and Action Integrity inputs.

***

**Step 3. Understand Your Score**

Your TCT score is determined by the TCE-26 standard in two layers.

* **Behavior determines your band:** Historical performance, current risk exposure, credit utilization, new credit activity account for 80% of your score. The remaining 20% is calculated using softer indicators such as investor status, collateral volatility, credit mix, and action integrity. Capital alone cannot move you into a higher band. Only behavior can.
* **Capacity determines your position within that band:** Your aggregate on-chain net worth, LP depth, verified cashflow, and transaction weight push your score toward the band ceiling and underwrite your Maximum Vouchsafed Value (MVV).

| Range   | Bracket   | CEW Action                                                   |
| ------- | --------- | ------------------------------------------------------------ |
| 800–850 | Excellent | <mark style="color:$success;">Enhancement</mark> (High)      |
| 740–799 | Very Good | <mark style="color:$success;">Enhancement</mark> (Low)       |
| 670–739 | Good      | <mark style="color:$primary;">Risk Neutral</mark>; No Change |
| 580–669 | Fair      | <mark style="color:$warning;">Enforcement</mark> (Low)       |
| 300–579 | Poor      | <mark style="color:$warning;">Enforcement</mark> (High)      |
| 1       | No Data   | <mark style="color:$info;">Credit Invisible</mark>           |
| 0       | Flagged   | <mark style="color:$danger;">Blocked</mark>                  |

Your score exists in two states at all times. Your **staged score** is computed continuously off-chain and is always current. Your **TCT balance** is the on-chain tokenized version, updated only when you Refresh. Integrated markets read your TCT balance, never your staged score.

Full formula breakdown in the [TCE-26 Standard](https://app.gitbook.com/s/pAHIYSR0KV9miINQoxWp/the-tythe-standard).

***

**Step 4. Refresh Your Score**

Refreshing mints your current staged score as your live TCT balance and MVV on-chain.

Hit **Refresh** on the Dashboard before opening a new position, before a rate negotiation, or when Tythe notifies you of a meaningful score increase. Here is what happens:

1. The backend computes the delta between your staged score and your current on-chain TCT balance
2. A signed EIP-712 attestation is generated
3. The attestation is passed to your wallet for submission
4. You sign and submit.&#x20;
5. Your TCT balance and MVV update on-chain

You pay the gas for all Refresh acts. No one else can refresh your score on your behalf. There is no benefit to refreshing constantly. Refresh at the right moment, not the most frequent one.

***

**Step 5. Put Your Score to Work**

With your TCT balance live, the Credit Enhancement Wrapper (CEW) applies automatically on every integrated market you interact with. It reads your score and MVV at transaction time and applies the corresponding action instantly. No manual application, no approval process.

* **Borrowers:** Lower interest rates and higher borrowing limits for high-TCT positions. Enhancements apply up to your MVV automatically.
* **Yield participants:** High-reliability depositors access enhanced yield tiers on integrated vaults.
* **Traders:** Tighter spreads, reduced margin requirements, and higher position limits for high-TCT traders on integrated exchanges.
* **RWA Investors:** Pool access and capital allocation tiers based on your TCT and MVV on integrated RWA platforms.

Your creditworthiness follows your CEP, not your geography. Any integrated market, anywhere.

***

**Protecting Your Score**

* **Auto-Slash is immediate and gasless:** A Liquidation, Default, or Exploit on any wallet linked to your CEP triggers an instant TCT reduction. No warning, no delay. A sudden slash may trigger automated adjustments on your active positions across integrated markets. Maintain healthy collateral ratios and avoid edge behavior.
* **Disputed slashes have a resolution path:** If you believe a slash was applied in error, raise a dispute with the Justice Arm of the Tythe DAO. AI clerks prepare an evidence brief from your on-chain data. A human jury drawn from your TCT band reviews the case and delivers a verdict. _Available in V1.2 (post-launch mechanic)_
* **Protect your score across wallet changes:** Your CEP is anchored to your root `did:cheqd` identity, not a single wallet. Before rotating addresses, link your latest EIP-712 scoring attestation to your DID as a DID-Linked Resource. This preserves your scoring relationship across the change. If the attestation is not linked before you lose access to a wallet, your score may not be recoverable.

***

**What's Coming**

**Tythe DAO & TYT Token** _(V1.2)_ TYT holders vote on protocol upgrades, fee parameters, and new feature proposals. As a TCT earner and protocol participant, your voice shapes what Tythe becomes. Tythe DAO Justice Arm handles contested slashes and scoring disputes.

**Credit Enhancement Vaults** _(V2)_ The only module enabling undercollateralized lending. Your TCT and MVV unlock credit lines beyond your posted collateral, backed by LP capital.

**Credit Data Licensing** _(V2)_ Anonymize and license your credit data to institutional researchers and AI engineers. Your data, your revenue.

***
{% endtab %}

{% tab title="Developers" %}
Credit-invisible users are your biggest source of avoidable risk. Tythe gives your protocol the infrastructure to change that. By replacing anonymous over-collateralization with verifiable, real-time creditworthiness that works at the smart contract level.

This guide covers the integration paths available to developers in V1 and how to use them to build credit-aware financial products.

***

#### What Tythe Gives You

Tythe exposes three on-chain primitives and one intelligence feed that developers can integrate independently or in combination:

| Primitive                        | What It Is                                                                                                                                                                           | What You Build With It                                    |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------- |
| CEP (Credit Enhancement Profile) | A permanent, sovereign financial identity anchored on `did:cheqd`. Resolves linked wallets, credentials, attestations, and financial history into one unified, accountable identity. | Permissioned market access, identity gating               |
| TCT (Tokenized Creditworthiness) | A non-transferable ERC-20 score (300–850) with embedded MVV                                                                                                                          | Risk-adjusted rates, dynamic LTV, credit-aware vaults     |
| CEW (Credit Enhancement Wrapper) | A smart contract proxy that applies TCT-based logic to financial positions                                                                                                           | Automated discounts, limit boosts, risk enforcement       |
| Relay Emitter                    | ML-powered real-time nEvent labels and percentile rankings broadcast to subscribers                                                                                                  | Live risk monitoring, default detection, risk-alpha feeds |

You do not need to integrate all four. Start with what your protocol needs.

***

#### Integration Path 1: CEP DID Resolution

**What you're doing:** Resolving an individual's complete financial identity to verify their standing before granting market access.

The CEP is anchored on the `did:cheqd` network. Each CEP maps a verified individual to one or more wallet addresses, compliance credentials, attestations, and financial history — all resolvable in a single call without touching raw personal data. Resolving a CEP gives your protocol a cryptographic confirmation that a wallet belongs to a verified individual with a complete, accountable financial identity.

**What resolution returns:**

* Verified KYC and sanctions status: confirmed via zero-knowledge attestation
* Proof of Personhood: confirmed human uniqueness
* Wallet-to-identity binding: every linked address maps to one verified root identity
* Linked attestations and credentials: compliance status, scoring attestations, and more

**Use cases:**

* Lending markets and derivatives that require verified, accountable participants
* Identity-gated vault and pool access without handling raw user data
* Compliance verification before executing high-value transactions

No raw PII ever touches your protocol. The ZK attestation is the only signal you need.

{% hint style="info" %}
#### Score portability across wallet changes

A user's CEP is anchored to their root did:cheqd identity, not a single wallet. If a user rotates or loses their primary wallet, their scoring relationship is preserved if they have linked the latest Tythe EIP-712 scoring attestation as a DID-Linked Resource. Their TCT balance can be reminted to a new primary address by presenting that attestation. Build your integration to resolve the CEP root identity (not the wallet address) as the persistent identifier for a user's credit state.
{% endhint %}

***

#### Integration Path 2: TCT & MVV Reading

**What you're doing:** Reading a user's creditworthiness score and protocol-assessed credit limit to power risk-adjusted financial logic.

**TCT (Credit Score):** TCT is a non-transferable ERC-20 token. Reading a user's TCT balance gives you their live credit score.&#x20;

**TCT Score Brackets:**

<table><thead><tr><th>Range</th><th width="200">Bracket</th><th>Suggested Action</th></tr></thead><tbody><tr><td>800–850</td><td>Excellent</td><td>High Boost</td></tr><tr><td>740–799</td><td>Very Good</td><td>Low Boost</td></tr><tr><td>670–739</td><td>Good</td><td>No Change</td></tr><tr><td>580–669</td><td>Fair</td><td>Risk Neutral</td></tr><tr><td>300–579</td><td>Poor</td><td>Negative Adjustment</td></tr><tr><td>1</td><td>No Data</td><td>Anonymous / Credit Invisible</td></tr><tr><td>0</td><td>Flagged</td><td>Hard Deny / Immediate Risk</td></tr></tbody></table>

**MVV (Credit Limit):** The Maximum Vouchsafed Value is embedded in the TCT token's metadata. It defines the maximum dollar value the Tythe protocol is willing to vouchsafe for that user's. Your protocol should never extend credit beyond the user's MVV; doing so means operating outside the protocol's risk assessment.

**Use cases:**

* Dynamic LTV adjustments
* Dynamic yield adjustments and allocation
* Tiered interest rates that reward high-reliability borrowers
* Credit-aware vault entry thresholds
* Risk-intel for DEX pairs and LP positions
* Size limits and fee discounts for prediction markets calibrated to user TCT

**How it works at the contract level:**

Call the standard ERC-20 `balanceOf` function on the TCT contract to read a user's score. Read the MVV from the token metadata. Use these values as inputs to your protocol's rate or limit logic.

{% hint style="info" %}
#### TCT is a live signal, not a static snapshot

A user's score can change between transactions (positively via Manual Refresh or negatively via Auto-Slash). Build your integration to read TCT at transaction time, not at session initiation.
{% endhint %}

***

#### Integration Path 3: CEW Integration

**What you're doing:** Deploying the Credit Enhancement Wrapper to automate credit-aware logic directly on your protocol's financial positions.

The CEW is a smart contract proxy that sits between your protocol and the user's transaction. It reads the user's credit data in real time and applies the appropriate credit enhancement or enforcement automatically.

**What the CEW applies:**

* **High TCT (Excellent / Very Good):** Rate discounts, limit boosts, reduced collateral requirements up to the user's MVV
* **Mid TCT (Good):** Risk-neutral pass-through, standard terms
* **Low TCT (Fair/Poor):** Negative adjustment, tighter terms, reduced limits
* **Slashed (0):** Hard deny, transaction blocked at the wrapper level

**Use cases:**

* RWA pools that want dynamic yield adjustments and allocation
* Lending markets that want to offer better rates to reliable borrowers without manual underwriting
* Vault products that automate LTV optimization based on creditworthiness
* DEX pairs that apply dynamic fee structures based on participant reliability
* Prediction markets using Tythe intel for dynamic size limits and&#x20;

**How it works at the contract level:**

Your protocol inherits or references the CEW contract. Incoming financial transactions are routed through the wrapper before execution. The CEW reads the initiating wallet's TCT balance, resolves the applicable bracket, and applies the corresponding logic before passing the transaction to your protocol's core execution layer. You can deploy it to apply boosts only, enforcement only, or both, depending on your protocol's risk appetite. Configuration options are covered in the CEW Technical Reference.

{% hint style="success" %}
#### CEW operates within the user's MVV at all times

It will never apply a boost that extends credit beyond what the protocol has vouchsafed for.
{% endhint %}

***

#### Integration Path 4: Relay Emitter Subscription

**What you're doing:** Subscribing to Tythe's real-time nEvent intelligence feed to monitor credit events across the ecosystem.

The Relay Emitter is an ML-powered intelligence layer built on gradient boosting models (XGBoost and LightGBM). It continuously monitors on-chain behavioral patterns, classifies negative credit events into labeled categories, and ranks each individual within their label's spectrum by severity. Labels and percentile rankings are delivered off-chain to your systems in real time.

**nEvent Typology:**

| Event       | Nature                                            | Signal Type                                      |
| ----------- | ------------------------------------------------- | ------------------------------------------------ |
| Liquidation | Collateral failure on an integrated market        | Auto-Slash triggered severity by percentile rank |
| Default     | Failure to fulfill debt within grace period       | Auto-Slash triggered severity by percentile rank |
| Exploit     | Verified involvement in smart contract attacks    | Blacklist triggered                              |
| Mercenary   | Rapid liquidity withdrawal during systemic stress | Alert; Velocity Risk flag                        |
| Informed    | Patterned high-alpha trades indicating toxic flow | Alert; metadata tag                              |
| Whale       | Objectively large on-chain transactions           | Alert; metadata tag                              |

**Each nEvent label includes:**

* CEP ID of the acting entity
* Event typology
* Percentile rank within the label's spectrum
* TCT Delta (the precise score change), where applicable
* Epoch Timestamp (cryptographic sequencing to prevent replay attacks)

**Use cases:**

* Real-time risk monitoring for lending markets and vault managers
* Early warning systems for default or exploit exposure
* Risk-alpha feeds for institutional capital allocators
* Automated position management triggered by nEvent alerts

**Access model:** The Relay Emitter is available to institutional subscribers via a tiered subscription feed. Integration details and pricing are available through the Tythe Developer Portal.

***

### Combining Integration Paths

The four paths are designed to be composable. Here are the most common combinations:

* **Credit-aware lending market:** CEP resolution (compliance gate) + TCT/MVV reading (risk-adjusted terms) + CEW (automated enforcement)
* **Risk-managed vault:** TCT/MVV reading (entry thresholds and LTV logic) + Relay Emitter (real-time default monitoring)
* **Permissioned RWA pool:** CEP resolution (KYC gate) + TCT/MVV reading (investor quality scoring) + CEW (dynamic yield allocation)
* **Institutional risk desk:** Relay Emitter (nEvent feed) + TCT reading (portfolio-level credit exposure monitoring)

***

### What's Coming for Developers

**APIs & SDKs** _(Roadmap)_ REST APIs and language-specific SDKs for web2-native integration will be released as the protocol grows and demand is established. If your stack requires API access ahead of the roadmap, reach out at [dev@tythe.network](mailto:dev@tythe.network).

**Tythe DAO & TYT Token** _**(V1.2):**_ TYT is the Tythe protocol token. Once live, developers and technical contributors participate in Tythe DAO governance; voting on technical specifications, integration standards, new primitive proposals, and protocol upgrade paths. Build with visibility into where the protocol is heading.

**CEV Integration** _**(V2):**_ Credit Enhancement Vaults will expose integration hooks for protocols that want to offer undercollateralized lending backed by LP capital. CEV integration will be available after V1 scoring data has matured.

**CDL Consumer Data&#x20;**_**(V2):**_ Developers and AI engineers will be able to access anonymized, licensed consumer credit data in multiple formats for model building, risk research, and quantitative analysis. Data is sovereign and user-consented; participants opt in to license their credit profiles and are compensated directly. Details on data formats, licensing tiers, and access will be published ahead of the V2 launch.

**Agentic Credit** _**(V2):**_ Verified AI agents will anchor to a CEP and leverage on-chain execution history for protocol-backed credit lines. The same primitives you build with today will serve agentic participants natively. No additional integration required.
{% endtab %}

{% tab title="Institutions" %}
Anonymous users are an expensive problem. Every position you size, every rate you set, every trade you clear, you're pricing in risk you cannot fully measure. Tythe gives you the infrastructure to measure it accurately.

This guide covers how on-chain institutions integrate Tythe's credit primitives to deploy smarter capital, reduce risk exposure, and build more competitive products.

***

#### What Tythe Gives You

Tythe exposes three on-chain primitives and one intelligence feed. Each addresses a specific capital efficiency or risk management problem.

| Primitive                        | What It Is                                                                                                                          | The Problem It Solves                                     |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| CEP (Credit Enhancement Profile) | A permanent, sovereign financial identity anchored on `did:cheqd`. Resolves a complete financial profile without exposing raw data. | Anonymous counterparties, fragmented financial identities |
| TCT (Tokenized Creditworthiness) | A non-transferable ERC-20 score (300–850) with embedded MVV                                                                         | Undifferentiated risk pricing, capital inefficiency       |
| CEW (Credit Enhancement Wrapper) | A smart contract proxy that applies TCT-based logic in real time                                                                    | Manual underwriting, static rate structures               |
| Relay Emitter                    | ML-powered real-time nEvent intelligence and percentile rankings broadcast to subscribers                                           | Delayed default detection, reactive risk management       |

***

#### Integration Path 1: CEP Resolution

**What you're doing:** Resolving an individual's complete financial identity before granting market access without handling any raw personal data.

Resolving a wallet's associated CEP gives your protocol a cryptographic confirmation that the individual is identity-verified, sanctions-screened, and carries a complete, accountable financial profile. The check is on-chain, gasless to read, and exposes zero PII to your system.

**Relevant for:** Lending markets, RWA pools, stablecoin issuers, and any institution operating permissioned markets.

**What resolution returns:**

* Verified KYC and sanctions status: confirmed via zero-knowledge attestation
* Proof of Personhood: confirmed human uniqueness
* Wallet-to-identity binding: every linked address maps to one verified root identity
* Linked attestations and credentials: compliance status, scoring attestations, and more

**The institutional advantage:** You resolve a complete financial identity without building or maintaining a KYC stack. No data liability. No raw PII. The ZK attestation is the only signal your protocol needs to process.

***

#### Integration Path 2: TCT & MVV Reading

**What you're doing:** Reading a participant's live creditworthiness score and protocol-assessed credit limit to power differentiated, risk-adjusted market logic.

TCT is a non-transferable ERC-20. Reading the balance gives you the score. Reading the metadata gives you the MVV (the maximum dollar value the Tythe protocol is willing to vouchsafe for that participant's position). Together, they are the most precise on-chain risk signal available.

**TCT Risk Brackets:**

| Range   | Bracket   | Institutional Signal                                      |
| ------- | --------- | --------------------------------------------------------- |
| 800–850 | Excellent | Highest reliability — maximum capital efficiency eligible |
| 740–799 | Very Good | Strong reliability — enhanced terms applicable            |
| 670–739 | Good      | Reliable — Standard terms                                 |
| 580–669 | Fair      | Risk neutral — tighter parameters recommended             |
| 300–579 | Poor      | Elevated risk — high scrutiny recommended                 |
| 1       | No Data   | Credit invisible — treat as anonymous                     |
| 0       | Flagged   | Hard risk signal — deny or restrict immediately           |

**Use cases by institution type:**

* **Lending Markets:** Dynamic LTV and interest rate tiers based on TCT bracket. High-reliability borrowers access better rates, you retain more competitive positions without increasing default exposure.
* **Vaults:** Credit-aware entry thresholds and yield allocation. High-TCT depositors can unlock enhanced yield tiers; high-TCT borrowers unlock lower collateral requirements up to their MVV.
* **CEXs:** Differentiated fee structures and trading limits. High-TCT traders access tighter spreads and higher position limits, rewarding reliable participants and reducing counterparty risk.
* **Prediction Markets:** Position size limits and fee discounts calibrated to TCT score. Reliable participants get better access; high-risk profiles face automatic position constraints.
* **Stablecoin Issuers:** Apply counterparty risk management for analyzing the risk profile of wallets interacting with your token (without needing to directly KYC every user), wallet mint limits, and wallet collateral requirements scaled to TCT and MVV.
* **RWA / DeFi Institutions:** Investor quality scoring for permissioned pools. TCT and MVV provide an objective, on-chain measure of participant reliability that complements your internal underwriting.

{% hint style="info" %}
#### TCT is a live signal

A participant's score can change between transactions (either positively via Manual Refresh or negatively via Auto-Slash). Always read TCT at transaction time, not at session initiation. Build your integration to reflect the current state, not a cached value.
{% endhint %}

***

#### Integration Path 3: CEW Integration

**What you're doing:** Deploying Tythe's Credit Enhancement Wrapper to automate credit-aware logic directly on your protocol's financial transactions without manual underwriting or static rate tables.

The CEW is a smart contract proxy. It intercepts incoming transactions, reads the participant's TCT score in real time, and applies the corresponding credit logic before execution reaches your protocol's core layer. The result is a fully automated, credit-differentiated market with zero manual intervention.

**What the CEW applies:**

| TCT Bracket | CEW Action                                                         |
| ----------- | ------------------------------------------------------------------ |
| Excellent   | <mark style="color:$success;">Enhancement</mark> (High)            |
| Very Good   | <mark style="color:$success;">Enhancement</mark> (Low)             |
| Good        | <mark style="color:$primary;">Risk Neutral</mark> (standard terms) |
| Fair        | <mark style="color:$warning;">Enforcement</mark> (Low)             |
| Poor        | <mark style="color:$warning;">Enforcement</mark> (High)            |
| Slashed     | <mark style="color:$danger;">Blocked</mark>                        |

**Use cases by institution/market type:**

* **DeFi Lending:** Automate LTV boosts and interest rate discounts for high-TCT borrowers. The CEW enforces risk controls for low-TCT positions without manual intervention.
* **DeFi Yield:** Apply dynamic entry logic and yield tiers based on participant creditworthiness. The CEW allocates vault access and terms automatically.
* **DeFi Staking:** Enforce participation thresholds based on TCT score. Reliable stakers access better terms; low-reliability profiles face automatic position constraints.
* **DeFi Insurance:** Apply dynamic premium and coverage limits based on TCT score at the point of entry. Reliable participants access lower premiums automatically.
* **Derivatives & Exchanges:** Apply spread reductions and fee discounts before trade execution. High-TCT traders receive better terms; the CEW enforces position limits for lower-reliability participants.
* **RWA Platforms:** Automate pool entry logic and capital allocation tiers based on participant credit profile and MVV.
* **Stablecoin Issuers:** Apply dynamic collateral ratios and mint limits based on TCT and MVV before issuance.
* **DAO Governance:** Enforce participation thresholds and voting weight based on verified identity and TCT score.

**The institutional advantage:** You stop pricing every user as an anonymous worst-case risk. High-reliability participants get better terms, making your protocol more competitive. Low-reliability participants face tighter controls, reducing your default and liquidation exposure. The CEW does both automatically, at the contract level, in real time.

{% hint style="success" %}
#### The CEW operates within MVV at all times

It will never apply a boost that extends credit beyond what the Tythe protocol has vouchsafed for a given participant. Your capital is never exposed beyond the protocol's assessed risk ceiling.
{% endhint %}

***

#### Integration Path 4: Relay Emitter Subscription

**What you're doing:** Subscribing to Tythe's real-time nEvent intelligence feed to monitor credit events across the ecosystem before they affect your positions.

The Relay Emitter is an ML-powered intelligence layer built on gradient boosting models (XGBoost and LightGBM). It monitors on-chain behavioral patterns, classifies negative credit events into labeled categories, and ranks each individual within their label's spectrum by severity. Labels and rankings are delivered directly to your risk systems in real time.

**nEvent Typology:**

| Event       | Nature                                            | Risk Signal                                        |
| ----------- | ------------------------------------------------- | -------------------------------------------------- |
| Liquidation | Collateral failure on an integrated market        | Auto-Slash triggered — severity by percentile rank |
| Default     | Failure to fulfill debt within grace period       | Hard Slash — reassess active positions             |
| Exploit     | Verified involvement in smart contract attacks    | Blacklist — terminate exposure immediately         |
| Mercenary   | Rapid liquidity withdrawal during systemic stress | Velocity Risk alert — monitor correlated positions |
| Informed    | Patterned high-alpha trades indicating toxic flow | Toxic flow alert — review counterparty exposure    |
| Whale       | Objectively large on-chain transactions           | Market impact alert — monitor liquidity            |

**Each label includes:**

* CEP ID of the acting entity
* Event typology
* Percentile rank within the label's spectrum
* TCT Delta (precise score change), where applicable
* Epoch Timestamp (cryptographic sequencing to prevent replay attacks)

**The institutional advantage:** You receive risk-alpha before it moves markets. A Default or Exploit label reaches your systems at the moment it is detected, not after the position has already moved against you. For institutions managing active exposure across multiple markets, the Relay Emitter is the difference between proactive and reactive risk management.

**Access model:** Relay Emitter access is available via tiered subscription with configurable data pool size, user count, and feed cadence. Contact the Tythe team via the Developer Portal for access and pricing.

***

**Recommended Integration Stack by Institution Type**

| Institution             | CEP Resolution | TCT & MVV | CEW      | Relay Emitter |
| ----------------------- | -------------- | --------- | -------- | ------------- |
| DeFi Lending            | ✓              | ✓         | ✓        | ✓             |
| DeFi Yield              | ✓              | ✓         | ✓        | ✓             |
| DeFi Staking            | ✓              | ✓         | ✓        | Optional      |
| DeFi Insurance          | ✓              | ✓         | ✓        | ✓             |
| Derivatives & Exchanges | ✓              | ✓         | ✓        | ✓             |
| RWA Platforms           | ✓              | ✓         | Optional | ✓             |
| Stablecoin Issuers      | ✓              | ✓         | ✓        | Optional      |
| DAO Governance          | ✓              | ✓         | Optional | Optional      |

***

### What's Coming for Institutions

**APIs & SDKs** _(Roadmap)_ REST APIs and language-specific SDKs for web2-native integration will be released as the protocol grows and demand is established. If your stack requires API access ahead of the roadmap, reach out at [business@tythe.network](mailto:dev@tythe.network).

**Tythe DAO & TYT Token&#x20;**_**(V1.2):**_ TYT is the Tythe protocol token. Institutional DAO members participate in Tythe governance with a specific mandate; voting on scoring formula parameters, weight adjustments, and protocol upgrade proposals. Institutional DAO members are the only participants with visibility into exact formula weights.

**Credit Enhancement Vaults (CEV)** _**(V2):**_ ERC-4626 vaults where LPs provide collateral top-offs to back TCT-verified borrowers. CEVs are the only module enabling undercollateralized lending on Tythe; risk is distributed across LPs who opt in for yield and risk premiums. Institutions never absorb default risk they did not explicitly underwrite. Launching after V1 scoring data has matured.

**Credit Data Licensing (CDL)&#x20;**_**(V2):**_ Institutional access to anonymized, user-consented credit data in structured formats for risk modeling, research, and AI training. Data is sovereign, participants opt in, and are compensated directly. Licensing tiers and format specifications will be published ahead of the V2 launch.

**Agentic Credit** _**(V2):**_ High-reputation AI agents with verified execution history will access credit through the same CEP/TCT/CEW stack as human participants. Institutions integrated with Tythe will automatically serve a new and growing class of creditworthy counterparty. No additional integration required.
{% endtab %}
{% endtabs %}
