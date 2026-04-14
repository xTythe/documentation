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

# Audience Guides

{% tabs %}
{% tab title="Individuals" %}
You are not a data point. You are not a passive subject in someone else's database. On Tythe, you are the sovereign owner of your financial reputation, and that reputation works for you.

This guide walks you through everything you need to go from zero to a fully active credit profile on Tythe, step by step.

***

#### What Tythe Does for You

In traditional finance, your credit score is owned by a bureau. In DeFi, you are treated as an anonymous risk regardless of your track record. Tythe replaces both with a single, verifiable, portable credit profile that you own, you control, and you put to work.

A high TCT score on Tythe means lower borrowing costs, better capital terms, and a financial reputation that travels with you across every integrated protocol and market, without ever exposing your private data.

***

#### Your Primitives

Before you get started, understand the tools that make up your Tythe profile:

**Credit Enhancement Profile (CEP):** Your sovereign credit identity. The CEP is your on-chain profile anchored to the `did:cheqd` network. It links your verified identity and wallet histories into a single, privacy-preserving financial footprint. Everything flows through here.

**Tokenized Creditworthiness (TCT):** Your on-chain credit score. A non-transferable ERC-20 token with a value between 300 and 850. It represents the creditworthiness you have earned through your on-chain behavior and chosen to tokenize. The higher your TCT, the better the capital terms available to you across integrated markets.

**Credit Enhancement Wrapper (CEW):** The transaction interceptor that puts your TCT to work in real time. When you interact with an integrated market, the CEW reads your TCT score and applies the appropriate boost (e.g., lower rates, higher limits, or reduced fees) automatically.

***

#### Step 1: Activate Your Profile

**What you're doing:** Creating your CEP and anchoring your identity to the protocol.

Go to the Tythe Dashboard and complete the following:

1. **zk-KYC via Privado ID.** Complete identity verification and sanctions screening. This is processed entirely via zero-knowledge attestation. Tythe never holds your raw identity data at any point.
2. **Connect your primary wallet.** Bind a primary wallet address to your CEP. This is the wallet the protocol will use as the anchor for your credit identity.

Once both steps are complete, your `did:cheqd` identifier is minted. This is your green light that your CEP is live and the scoring engine is active on your profile.

***

#### Step 2: Build Your Profile

**What you're doing:** Giving the protocol the data it needs to score you accurately.

Your CEP pulls on-chain data from your connected wallets automatically. But the more signal you give it, the stronger your profile becomes. Here is what you can add:

* **Connect additional wallets:** If you use multiple wallets across different protocols, connect them all. A wallet you use on Aave that isn't linked to your CEP is creditworthiness the protocol cannot see and cannot reward you for. Multi-wallet connectivity also signals responsible on-chain security behavior, which positively affects your Action Integrity score.

{% hint style="danger" %}
#### Link every active wallet

Tythe's CEW only applies boosts to interactions made from wallets linked to your CEP. If you borrow on Morpho using a wallet that isn't connected, that market sees you as anonymous and credit invisible; you receive zero benefit from your actual TCT score. Use the dashboard to aggregate all active addresses. Linking a wallet is a simple, one-time transaction.
{% endhint %}

* **Add Proof of Personhood (PoP).** Connect a verified World ID or equivalent biometric credential to your CEP. This is optional, but it grants a fixed **+5 TCT boost** to your score and strengthens your profile's Sybil resistance.
* **Log manual activity.** Use the Data tab on the Tythe Dashboard to manually record financial activity the protocol cannot yet pull automatically. This includes RWA actions (ownership, exposure, management, and retention) across platforms like Centrifuge, with Maple Finance, Ondo, Theo, and other major players added as the protocol grows. It also includes DeFi activity on protocols and chains not yet natively supported by Tythe. The richer your logged history, the more complete your credit picture, and the more accurately the protocol can score your Investor Status, Credit Mix, and Action Integrity inputs.

***

#### Step 3: Understand Your Score

**What you're doing:** Learning what drives your TCT and how to grow it.

Your TCT score (300–850) is determined by the TCE-26 standard. The formula is two-tiered:

**Your behavior determines your band:** Historical performance, current risk exposure, credit utilization, and new credit activity account for 80% of your score. These inputs measure the quality and consistency of your on-chain behavior over time. Capital alone cannot move you into a higher band, only behavior can.

**Your capacity determines your position within that band.** Your aggregate on-chain net worth, LP depth, verified cashflow, and transaction weight push your score toward the ceiling of your reliability band and underwrite your Maximum Vouchsafed Value (MVV); the protocol's assessed credit limit for your position.

The full scoring breakdown is available in the [TCE-26 Standard](../the-tythe-standard.md).

{% hint style="info" %}
#### Your score exists in two states.

Your _staged score_ is your off-chain creditworthiness which is continuously updated by the protocol as your behavior changes. Your _TCT balance_ is the on-chain tokenized version of that score which is updated only when you choose to Refresh. The staged score is always current. The TCT balance reflects your score at the last time you chose to tokenize it.
{% endhint %}

***

#### Step 4: Tokenize Your Creditworthiness

**What you're doing:** Minting your current staged score onto the blockchain as your live TCT balance.

When you are ready to use your creditworthiness before opening a new credit line, applying for a rate discount, or demonstrating reliability to an integrated market, hit **Refresh** on the Tythe Dashboard.

Here is what happens:

1. Tythe's backend calculates the current delta between your staged score and your on-chain TCT balance.
2. A human-readable EIP-712 attestation is generated and signed.
3. The signed attestation is passed to your wallet for submission.
4. You submit the transaction to the blockchain. Your TCT balance updates.

You pay the gas for this transaction. It is your sovereign act of tokenizing your own creditworthiness; the protocol does not do it for you, and no one else can do it on your behalf.

{% hint style="info" %}
#### Refresh strategically, not constantly

There is no benefit to refreshing every day. Refresh when it matters: before a new credit position, before a rate negotiation, or when Tythe notifies you of a significant score increase. Save gas by refreshing at the right moment, not the most frequent one.
{% endhint %}

***

#### Step 5: Put Your TCT to Work

**What you're doing:** Using your score to access better capital terms across integrated markets.

Once your TCT balance is live, the CEW goes to work automatically on every integrated market you interact with.

**Borrowers:** CEW reads your TCT at the point of every loan interaction. A high score unlocks lower interest rates and higher borrowing limits automatically, without manual application or approval.

**Yield Participants:** High-TCT depositors access enhanced yield tiers on integrated vaults. Your reliability earns you better allocation, not just access.

**Traders:** On integrated exchanges, TCT unlocks tighter spreads, reduced margin requirements, and higher position limits. Your track record becomes an execution advantage.

**RWA Investors:** Integrated RWA platforms use your TCT and MVV to determine pool access and capital allocation tiers. Your on-chain history speaks before you do.

> **Your Score Travels With You:** Whether you're on Morpho, Lido, Centrifuge, or any integrated Uniswap DEX pair, your creditworthiness is readable by any integrated protocol globally. Your TCT follows your CEP, not your geography.

***

#### Protecting Your Score

Here is some important information you need to know about.

**Negative events trigger automatic slashes.** If the protocol detects a Liquidation, Default, or Exploit on any wallet linked to your CEP, it bypasses the Refresh process and immediately burns a portion of your TCT balance. This happens automatically with no warning and no delay. The enforcement is protocol-side and gasless.

**Slashed TCT affects your active positions.** A sudden TCT reduction may trigger automated margin calls or CEW adjustments on your active positions on integrated markets. Maintain healthy collateral ratios and avoid edge-behavior to protect your score.

**Disputed slashes have a path to resolution.** If you believe a slash was applied in error, you can raise a dispute with the Justice Arm of the Tythe DAO. AI clerks prepare an evidence brief from your on-chain data. A human jury drawn from your TCT band reviews the case and delivers a verdict. You do not need a lawyer, just your on-chain history.

**Protect your score across wallet changes.** Your CEP is anchored to your root did:cheqd identity, not a single wallet. If you lose access to your primary wallet or choose to rotate addresses, any linked secondary wallet can be promoted to primary via the Tythe Dashboard. To preserve your TCT scoring relationship across wallet changes, link the latest Tythe EIP-712 scoring attestation to your DID as a DID-Linked Resource. If the attestation is linked, your TCT balance can be reminted to a new primary address. If it is not linked, your score may not be recoverable. Linking the attestation is a sovereign action; only you can do it, and only you benefit from it.

***

#### What's Coming for Individuals

The following features are on the Tythe roadmap and not yet live:

**Tythe DAO & TYT Token** _**(V1.2):**_ TYT is the Tythe protocol token. Once live, TYT holders participate in Tythe DAO governance; voting on protocol upgrades, fee parameters, new feature proposals, and the general direction and growth of the protocol. As a TCT earner and protocol participant, your voice shapes what Tythe becomes.

**Credit Vouchers&#x20;**_**(V1.2):**_ Verified institutions such as banks, fintechs, and funds, will be able to issue on-chain attestations vouching for your creditworthiness based on their internal due diligence. A Credit Voucher from a trusted institution will directly strengthen your CEP and TCT.

**Credit Data Licensing** _**(V2):**_ Choose to anonymize and license your credit data to institutional researchers, model builders, and AI engineers, and get paid for it. Your data, your revenue.

**Credit Enhancement Vaults&#x20;**_**(V2):**_ The only module on Tythe that enables undercollateralized lending. LPs provide collateral top-offs to back high-TCT borrowers; meaning your proven reliability can unlock credit lines that go beyond your posted collateral.
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

TCT is a non-transferable ERC-20 token. Reading a user's TCT balance gives you their live credit score. Reading the MVV embedded in the token's metadata gives you the protocol's assessed dollar credit limit for that user and their position. Your protocol should never extend credit beyond the user's MVV (doing so means operating outside the protocol's risk assessment).

**TCT Score Brackets:**

<table><thead><tr><th>Range</th><th width="200">Bracket</th><th>Suggested Action</th></tr></thead><tbody><tr><td>800–850</td><td>Excellent</td><td>High Boost</td></tr><tr><td>740–799</td><td>Very Good</td><td>Low Boost</td></tr><tr><td>670–739</td><td>Good</td><td>No Change</td></tr><tr><td>580–669</td><td>Fair</td><td>Risk Neutral</td></tr><tr><td>300–579</td><td>Poor</td><td>Negative Adjustment</td></tr><tr><td>1</td><td>No Data</td><td>Anonymous / Credit Invisible</td></tr><tr><td>0</td><td>Slashed</td><td>Hard Deny / Immediate Risk</td></tr></tbody></table>

**MVV (Credit Limit):** The Maximum Vouchsafed Value is embedded in the TCT token's metadata. It defines the maximum dollar value the Tythe protocol is willing to vouchsafe for that user's position. Your protocol should never extend credit beyond the user's MVV; doing so means operating outside the protocol's risk assessment.

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

The Relay Emitter is an ML-powered intelligence layer built on gradient boosting models (XGBoost and LightGBM) — not a blockchain feature. It continuously monitors on-chain behavioral patterns, classifies negative credit events into labeled categories, and ranks each individual within their label's spectrum by severity. Labels and percentile rankings are delivered off-chain to your systems in real time.

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

**Credit-aware lending market:** CEP resolution (compliance gate) + TCT/MVV reading (risk-adjusted terms) + CEW (automated enforcement)

**Risk-managed vault:** TCT/MVV reading (entry thresholds and LTV logic) + Relay Emitter (real-time default monitoring)

**Permissioned RWA pool:** CEP resolution (KYC gate) + TCT/MVV reading (investor quality scoring) + CEW (dynamic yield allocation)

**Institutional risk desk:** Relay Emitter (nEvent feed) + TCT reading (portfolio-level credit exposure monitoring)

***

### What's Coming for Developers

**APIs & SDKs** _(Roadmap)_ REST APIs and language-specific SDKs for web2-native integration will be released as the protocol grows and demand is established. If your stack requires API access ahead of the roadmap, reach out at [dev@tythe.network](mailto:dev@tythe.network).

**Tythe DAO & TYT Token** _**(V1.2):**_ TYT is the Tythe protocol token. Once live, developers and technical contributors participate in Tythe DAO governance; voting on technical specifications, integration standards, new primitive proposals, and protocol upgrade paths. Build with visibility into where the protocol is heading.

**Credit Voucher Verification&#x20;**_**(V1.2):**_ Protocols will be able to verify institutional Credit Vouchers as part of their workflow allowing vouched users to access enhanced terms on top of their TCT score.

**CEV Integration** _**(V2):**_ Credit Enhancement Vaults will expose integration hooks for protocols that want to offer undercollateralized lending backed by LP capital. CEV integration will be available after V1 scoring data has matured.

**Agentic Credit** _**(V2):**_ Verified AI agents will anchor to a CEP and leverage on-chain execution history for protocol-backed credit lines. The same primitives you build with today will serve agentic participants natively. No additional integration required.

**CDL Consumer Data&#x20;**_**(V2):**_ Developers and AI engineers will be able to access anonymized, licensed consumer credit data in multiple formats for model building, risk research, and quantitative analysis. Data is sovereign and user-consented; participants opt in to license their credit profiles and are compensated directly. Details on data formats, licensing tiers, and access will be published ahead of the V2 launch.
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
| 0       | Slashed   | Hard risk signal — deny or restrict immediately           |

**Use cases by institution type:**

* **Lending Markets:** Dynamic LTV and interest rate tiers based on TCT bracket. High-reliability borrowers access better rates — you retain more competitive positions without increasing default exposure.
* **Vaults:** Credit-aware entry thresholds and yield allocation. High-TCT depositors can unlock enhanced yield tiers; high-TCT borrowers unlock lower collateral requirements up to their MVV.
* **CEXs:** Differentiated fee structures and trading limits. High-TCT traders access tighter spreads and higher position limits — rewarding reliable participants and reducing counterparty risk.
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

| TCT Bracket | CEW Action                                                           |
| ----------- | -------------------------------------------------------------------- |
| Excellent   | High Boost (maximum rate discount, limit boost, or spread reduction) |
| Very Good   | Low Boost                                                            |
| Good        | Risk Neutral (standard terms)                                        |
| Fair        | Low Negative Adjustment                                              |
| Poor        | High Negative Adjustment                                             |
| Slashed     | Hard Deny  (transaction blocked)                                     |

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

The Relay Emitter is an ML-powered intelligence layer built on gradient boosting models (XGBoost and LightGBM) — not a blockchain feature. It monitors on-chain behavioral patterns, classifies negative credit events into labeled categories, and ranks each individual within their label's spectrum by severity. Labels and rankings are delivered directly to your risk systems in real time.

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

**Tythe DAO & TYT Token&#x20;**_**(V1.2):**_ TYT is the Tythe protocol token. Institutional DAO members participate in Tythe governance with a specific mandate — voting on scoring formula parameters, weight adjustments, and protocol upgrade proposals. Institutional DAO members are the only participants with visibility into exact formula weights. TYT staking is also the accountability mechanism behind Credit Voucher issuance — vouching institutions stake TYT and lose it on inaccurate vouchers.

**Credit Vouchers&#x20;**_**(V1.2):**_ Verified institutions (banks, fintechs, funds, and merchants) will be able to issue on-chain EIP-712 attestations vouching for participants based on internal due diligence or performance logs. Vouching institutions stake TYT protocol tokens, creating direct accountability for voucher accuracy. Full details in the Credit Voucher module documentation.

**Credit Enhancement Vaults (CEV)** _**(V2):**_ ERC-4626 vaults where LPs provide collateral top-offs to back TCT-verified borrowers. CEVs are the only module enabling undercollateralized lending on Tythe; risk is distributed across LPs who opt in for yield and risk premiums. Institutions never absorb default risk they did not explicitly underwrite. Launching after V1 scoring data has matured.

**Agentic Credit** _**(V2):**_ High-reputation AI agents with verified execution history will access credit through the same CEP/TCT/CEW stack as human participants. Institutions integrated with Tythe will automatically serve a new and growing class of creditworthy counterparty. No additional integration required.

**Credit Data Licensing (CDL)&#x20;**_**(V2):**_ Institutional access to anonymized, user-consented credit data in structured formats for risk modeling, research, and AI training. Data is sovereign, participants opt in, and are compensated directly. Licensing tiers and format specifications will be published ahead of the V2 launch.
{% endtab %}
{% endtabs %}
