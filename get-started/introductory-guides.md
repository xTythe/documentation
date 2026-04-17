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
Tythe gives your protocol verifiable, real-time credit intelligence at the smart contract level. This guide covers what Tythe exposes to developers and which primitive solves which problem.

***

**What Tythe Exposes**

Three on-chain primitives and one off-chain intelligence feed. Integrate one or all — they are composable by design.

**CEP (Credit Enhancement Profile):** Sovereign financial identity anchored on `did:cheqd`. Resolves any wallet to its verified owner, compliance status, and linked resources. The identity layer everything else builds on.

**TCT (Tokenized Creditworthiness):** Non-transferable ERC-20 score (300–850) with MVV embedded in token metadata. The live credit signal your contracts read at transaction time.

**CEW (Credit Enhancement Wrapper):** Smart contract proxy. Intercepts transactions, reads TCT, and applies credit logic automatically. Inherit CEW without re-architecting your stack.

**Relay Emitter:** Off-chain ML-powered nEvent feed. Classifies and labels negative credit events in real time and delivers structured signals to your systems the moment they are detected.

***

**1. CEP**

Call `resolveWallet(address wallet)` on the Attestation Registry. Returns the wallet's associated `did:cheqd` identifier and primary wallet address. Returns `("", address(0))` for any unlinked wallet; treat these as anonymous.

What resolution confirms:

* Verified KYC and sanctions status via zero-knowledge attestation
* Proof of Personhood confirmed human uniqueness
* Wallet-to-identity binding. Every linked address maps to one verified root DID

**Build to the DID, not the wallet address.** A participant's CEP persists across wallet rotations. The DID is the persistent identifier for a participant's credit state.

No raw PII ever touches your protocol. The ZK attestation is the only signal your system processes.

{% hint style="info" %}
**Use when:** Your protocol needs to verify a participant is a real, KYC-compliant individual before granting access to lending markets, RWA pools, permissioned vaults, stablecoin issuers.
{% endhint %}

***

**2. TCT & MVV**

Call <mark style="color:red;">`balanceOf(address wallet)`</mark> on the TCT Contract to read the score. Call <mark style="color:red;">`getMVV(address wallet)`</mark> to read the MVV in USD, 18 decimals.

**Score brackets:**

| Range   | Bracket   | CEW Action                                                   |
| ------- | --------- | ------------------------------------------------------------ |
| 800–850 | Excellent | <mark style="color:$success;">Enhancement</mark> (High)      |
| 740–799 | Very Good | <mark style="color:$success;">Enhancement</mark> (Low)       |
| 670–739 | Good      | <mark style="color:$primary;">Risk Neutral</mark>; No Change |
| 580–669 | Fair      | <mark style="color:$warning;">Enforcement</mark> (Low)       |
| 300–579 | Poor      | <mark style="color:$warning;">Enforcement</mark> (High)      |
| 1       | No Data   | <mark style="color:$info;">Credit Invisible</mark>           |
| 0       | Flagged   | <mark style="color:$danger;">Blocked</mark>                  |

* **MVV is an enhancement ceiling, not a transaction gate.** \
  Transactions above a participant's MVV still proceed, enhancement applies up to MVV, the remainder transacts at standard terms. Never treat MVV as a block.&#x20;
* **Read at transaction time, not session initiation.** \
  Scores update between transactions — positively via Manual Refresh, negatively via Auto-Slash. A cached value is stale the moment a score changes.

Additional read functions: <mark style="color:red;">`isEligible(address, uint256 minTCT)`</mark>, <mark style="color:red;">`isBlacklisted(address)`</mark>, <mark style="color:red;">`getScoreBracket(address)`</mark>.

{% hint style="info" %}
**Use when:** Your protocol needs differentiated risk pricing (such as dynamic LTV, tiered interest rates, credit-aware vault thresholds, stablecoin mint limits, DEX fee structures, yield allocation).
{% endhint %}

***

**3. CEW**

Inherit the CEW interface. Your market is registered via <mark style="color:red;">`registerMarket()`</mark> with a <mark style="color:red;">`MarketConfig`</mark> specifying <mark style="color:red;">`maxBoostBps`</mark>, <mark style="color:red;">`maxReductionBps`</mark>, <mark style="color:red;">`enforceBlock`</mark>, and <mark style="color:red;">`feeToken`</mark>.

Call <mark style="color:red;">`getCreditAction(uint256 value)`</mark> from within your transaction logic to get a <mark style="color:red;">`CreditAction`</mark> (action type, magnitude in basis points, and MVV ceiling) without modifying state. <mark style="color:red;">`msg.sender`</mark> is the participant, <mark style="color:red;">`address(this)`</mark> is the market.

**Action types and bracket mapping:**



<table><thead><tr><th width="120">Bracket</th><th width="374">Action</th><th>Magnitude</th></tr></thead><tbody><tr><td>Excellent</td><td>HighBoost if <mark style="color:red;"><code>maxBoostBps >= 600</code></mark>, <br>LowBoost if <mark style="color:red;"><code>maxBoostBps &#x3C; 600</code></mark></td><td>maxBoostBps or maxBoostBps / 2</td></tr><tr><td>Very Good</td><td>LowBoost</td><td>maxBoostBps / 2</td></tr><tr><td>Good</td><td>Neutral</td><td>0</td></tr><tr><td>Fair</td><td>LowReduction if <mark style="color:red;"><code>maxReductionBps &#x3C; 600</code></mark>, HighReduction if <mark style="color:red;"><code>maxReductionBps >= 600</code></mark></td><td>maxReductionBps or maxReductionBps / 2</td></tr><tr><td>Poor</td><td>HighReduction</td><td>maxReductionBps</td></tr><tr><td>No Data</td><td>Neutral</td><td>0</td></tr><tr><td>Flagged</td><td>Block if <mark style="color:red;"><code>enforceBlock = true</code></mark>, <br>HighReduction if <mark style="color:red;"><code>enforceBlock = false</code></mark></td><td>0 or maxReductionBps</td></tr></tbody></table>

* **On Block:** CEW returns <mark style="color:red;">`CreditAction(Block)`</mark> (it does not revert). Your protocol must implement the revert in your own execution logic after reading the returned action type.
* **Fee switch:** CEW launches fee-free. When the Tythe DAO activates the fee-switch, a flat 0.07% applies to all three action types. Enhancement fee paid by the individual participant on-chain at transaction time, Enforcement and Blocker fees tracked off-chain and invoiced monthly to your market.

{% hint style="info" %}
**Use when:** Your protocol wants automated, credit-differentiated execution without rebuilding core logic (lending markets, vaults, exchanges, RWA pools, prediction markets).
{% endhint %}

***

**4. Relay Emitter**

Off-chain intelligence feed. Subscribe via the Tythe Portal. Labels and percentile rankings delivered to your systems in real time.

**nEvent types:**

<table><thead><tr><th width="135">Event</th><th>Trigger</th><th>Enforcement</th></tr></thead><tbody><tr><td>Liquidation</td><td>Collateral failure on an integrated market</td><td>Auto-Slash (severity by percentile rank)</td></tr><tr><td>Default</td><td>Loan not repaid within grace period</td><td>Auto-Slash (severity by percentile rank)</td></tr><tr><td>Exploit</td><td>Verified protocol attack involvement</td><td>Blacklist</td></tr><tr><td>Mercenary</td><td>Rapid liquidity withdrawal under stress</td><td>Alert only (Velocity Risk flag)</td></tr><tr><td>Informed</td><td>Patterned high-alpha toxic flow</td><td>Alert only (metadata tag)</td></tr><tr><td>Whale</td><td>Objectively large on-chain transaction</td><td>Alert only (metadata tag)</td></tr></tbody></table>

Each label includes CEP ID, event typology, percentile rank within the label spectrum, TCT delta where applicable, and epoch timestamp for replay prevention.

{% hint style="info" %}
**Use when:** Your protocol needs early warning on counterparty credit deterioration (lending markets, vault managers, institutional risk desks).
{% endhint %}

***

### Combining Integration Paths

The four paths are designed to be composable. Here are the most common combinations:

* **Credit-aware lending market:** CEP resolution (eligibility gate) + TCT/MVV reading (risk-adjusted terms) + CEW (automated enforcement)
* **Risk-managed vault:** TCT/MVV reading (entry thresholds and LTV logic) + Relay Emitter (real-time default monitoring)
* **Permissioned RWA pool:** CEP resolution (KYC gate) + TCT/MVV reading (investor quality scoring) + CEW (dynamic yield allocation)
* **Institutional risk desk:** Relay Emitter (nEvent feed) + TCT/MVV reading (portfolio-level credit exposure monitoring)

***

**What's Coming**

**APIs & SDKs** _(Roadmap):_ REST APIs and language-specific SDKs for web2-native integration. Contact [dev@tythe.network](mailto:dev@tythe.network) if your stack requires API access ahead of the roadmap.

**Tythe DAO & TYT Token** _(V1.2):_ Vote on technical specifications, integration standards, and protocol upgrade paths.

**CEV Integration** _(V2):_ Integration hooks for protocols offering undercollateralized lending backed by LP capital.

**Credit Data Licensing** _(V2):_ Anonymized, user-consented credit data for model building and risk research.

**Agentic Credit** _(V2):_ AI agents access credit through the same primitives. No additional integration required.
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
