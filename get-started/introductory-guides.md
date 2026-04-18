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
Tythe gives you a financial reputation that works for you. This guide walks you from zero footprint to active value; your profile set up and your live scores and limits working across every integrated market.

***

**What You're Building on Tythe**

Five things come together to make your Tythe profile work.

1. **Credit Enhancement Profile (CEP):** Your sovereign financial identity. Anchored on the `did:cheqd` network, your CEP links your verified identity, your wallets, your credentials, and your credit history into one portable, privacy-preserving profile. You own it permanently. No institution holds it for you.
2. **Tokenized Creditworthiness (TCT)** Your on-chain credit character score. A non-transferable token between 300 and 850, earned through seven behavioral inputs (historical performance, current risk exposure, credit utilization, new credit activity, volatility quotient, credit mix, and action integrity). TCT governs your terms on lending markets, exchanges, insurance protocols, and card issuers.
3. **Tokenized Investment Quality (TIQ):** Your on-chain investment quality score. A non-transferable value between 300 and 850, measuring the reliability and performance of your capital deployment across RWA platforms and yield vaults. TIQ governs your terms on integrated RWA platforms and investment-oriented markets.
4. **Tokenized Liquidity Quality (TLQ):** Your on-chain liquidity quality score. A non-transferable value between 300 and 850, measuring the consistency and depth of your liquidity provision across DEX pairs and LP positions. TLQ governs your terms on integrated DEX pairs and LP markets.
5. **Maximum Vouchsafed Value (MVV)** Your per-transaction enhancement ceiling. Sized by the scoring engine at one-tenth of your 30-day rolling credit capacity, which is derived from your capital capacity markers (net worth, LP depth, verified cashflow, investor status, and transaction weight). When CEW applies a value-based enhancement, it applies up to your MVV. Transactions above MVV still go through; the enhancement covers the MVV portion, the remainder transacts at standard terms.

***

**Step 1. Create Your CEP**

Go to the Tythe Dashboard and complete two steps:

1. **zk-KYC via Billions.** Identity verification and sanctions screening, processed entirely via zero-knowledge attestation. Tythe never holds your raw identity data at any point.
2. **Connect your primary wallet.** Bind a wallet address to your CEP as your on-chain anchor.

Once both are done, your `did:cheqd` identifier is minted. Your CEP is live and the scoring engine is active on your profile.

***

**Step 2. Build Your Profile**

Your CEP pulls on-chain data from connected wallets automatically. The stronger your signal, the more accurately the protocol scores you across all four values (TCT, TIQ, TLQ, and MVV).

* **Link every active wallet:** A wallet you use on Morpho that is not linked to your CEP is creditworthiness the protocol cannot see and cannot reward you for. CEW only applies enhancements to wallets linked to your CEP. Unlinked addresses are treated as anonymous regardless of your actual scores. Link all active addresses once via the Dashboard.
* **Add Proof of Personhood:** Connect a World ID or equivalent biometric credential for a fixed **+5 TCT boost** and stronger Sybil resistance. Optional but recommended.
* **Log manual activity:** Use the Data tab to record financial activity the protocol cannot yet pull automatically, such as RWA positions on Centrifuge, Maple, Ondo, and other platforms not yet natively supported. Richer history means more accurate scoring across your Credit Mix, Action Integrity, and TIQ inputs.
* **zkTLS off-chain verifications** _(Coming post-launch):_ Once live, zkTLS will allow you to verify off-chain financial data (bank statements, income records, payroll, and more) directly to your CEP without exposing the underlying documents. This expands your scoring surface beyond on-chain activity and strengthens your TCT, TIQ, TLQ, and MVV for participants with strong off-chain financial histories that on-chain data alone cannot capture.

***

**Step 3. Understand Scores & Limits**

* **TCT** is your character score. Seven behavioral inputs determine your band. Capital alone cannot move you into a higher band. Only behavior earns it.
* **TIQ** is your investment quality score. It reflects the quality of your capital deployment across RWA platforms and yield vaults.
* **TLQ** is your liquidity quality score. It reflects the quality of your liquidity provision across DEX pairs and LP positions.

TCT, TIQ, and TLQ all use the same 300-850 bracket scale:

| Range   | Bracket   | CEW Action                                                   |
| ------- | --------- | ------------------------------------------------------------ |
| 800–850 | Excellent | <mark style="color:$success;">Enhancement</mark> (High)      |
| 740–799 | Very Good | <mark style="color:$success;">Enhancement</mark> (Low)       |
| 670–739 | Good      | <mark style="color:$primary;">Risk Neutral</mark>; No Change |
| 580–669 | Fair      | <mark style="color:$warning;">Enforcement</mark> (Low)       |
| 300–579 | Poor      | <mark style="color:$warning;">Enforcement</mark> (High)      |
| 1       | No Data   | <mark style="color:$info;">Credit Invisible</mark>           |
| 0       | Flagged   | <mark style="color:$danger;">Blocked</mark>                  |

* **MVV** is your per-transaction enhancement limit, expressed as a dollar amount. It reflects your capital capacity and determines the maximum dollar value of any value-based discount CEW will apply on a single transaction. MVV is not scored on a bracket. It is a hard ceiling that CEW reads independently alongside your bracket score.

Your scores and limits exist in two states. Your **staged scores & limits** are computed continuously off-chain and are always current. Your **on-chain balance & values** are updated only when you Refresh. Integrated markets read your on-chain balances and values.

Full formula breakdown in the [TCE-26 Standard](https://app.gitbook.com/s/pAHIYSR0KV9miINQoxWp/the-tythe-standard).

***

**Step 4. Refresh Scores & Limits**

Refreshing mints your current staged scores and limits as your live on-chain balances. One transaction updates TCT, MVV, TIQ, and TLQ simultaneously.

Hit **Refresh** on the Dashboard before opening a new position, before a rate negotiation, or when Tythe notifies you of a meaningful score increase. Here is what happens:

1. The scoring engine computes the current values for TCT, MVV, TIQ, and TLQ
2. A signed EIP-712 attestation is generated carrying all four values
3. The attestation is passed to your wallet for submission
4. You sign and submit. TCT, MVV, TIQ, and TLQ update on-chain atomically

You pay the gas. No one else can refresh your scores on your behalf. Refresh at the right moment, not the most frequent one.

***

**Step 5. Put Scores & Limits to Work**

With your on-chain balances live, the Credit Enhancement Wrapper (CEW) applies automatically on every integrated market you interact with. It reads the relevant score and MVV at transaction time and applies the corresponding action instantly. No manual application, no approval process.

Each integrated market configures which signal CEW reads (TCT, TIQ, or TLQ) based on what is most relevant to their product. MVV governs value-based enhancements regardless of which signal the market reads.

**CEW applies two types of discounts:**

* **Value-based:** A percentage reduction on dollar-denominated parameters, such as collateral required, fees charged, premiums. Applied up to your MVV per transaction.
* **Rate-based:** A percentage reduction on interest rates. No MVV cap, your character score alone governs rate discounts.

**By market type:**

* **Lending markets** read TCT. High-TCT borrowers access lower interest rates and reduced collateral requirements automatically.
* **Exchanges and derivatives** read TCT. High-TCT traders access tighter spreads and reduced margin requirements.
* **Insurance protocols** read TCT. High-TCT participants access lower premiums automatically.
* **Card issuers** read TCT and MVV. High-TCT cardholders access higher credit limits and better fee structures.
* **RWA platforms** read TIQ. High-TIQ investors access better pool terms and yield allocations.
* **DEX pairs and LP markets** read TLQ. High-TLQ liquidity providers access better fee structures and position terms.

Your creditworthiness follows your CEP, not your geography. Any integrated market, anywhere.

***

**Protecting Your Score**

*   **Auto-Slash is immediate and gasless.** Negative events on any wallet linked to your CEP trigger instant score reductions with no warning and no delay. Different events affect different scores:

    * Liquidation and Default slash TCT
    * Exploit blacklists your CEP and sets TCT to zero
    * Mercenary withdrawals slash TLQ
    * Informed trading patterns slash TIQ
    * Whale events flag TIQ and TLQ with alerts

    A sudden slash may trigger automated adjustments on your active positions across integrated markets. Maintain healthy collateral ratios, avoid edge behavior, and do not withdraw liquidity aggressively during systemic stress.
* **Disputed slashes have a resolution path.** If you believe a slash was applied in error, raise a dispute with the Justice Arm of the Tythe DAO. AI clerks prepare an evidence brief from your on-chain data. A human jury drawn from your TCT band reviews the case and delivers a verdict. Available in V1.2.
* **Protect your scores across wallet changes.** Your CEP is anchored to your root `did:cheqd` identity, not a single wallet. Before rotating addresses, link your latest EIP-712 scoring attestation to your DID as a DID-Linked Resource. This preserves your scoring relationship across the change. If the attestation is not linked before you lose access to a wallet, your scores may not be recoverable.

***

**What's Coming**

**Tythe DAO and TYT Token** _(V1.2):_ TYT holders vote on protocol upgrades, fee parameters, and new feature proposals. The Justice Arm handles contested slashes and scoring disputes.

**Credit Enhancement Vaults** _(V2):_ The only module enabling undercollateralized lending. Your TCT and MVV unlock credit lines beyond your posted collateral, backed by LP capital.

**Credit Data Exchange** _(V3):_ Sell your verified credit data to institutional buyers for risk modeling, agent and model training, and credit event patterning. Your data, your revenue.
{% endtab %}

{% tab title="Integration Guide (For Developers)" %}
Tythe gives your protocol verifiable, real-time credit intelligence at the smart contract level. This guide covers what Tythe exposes to developers and which primitive solves which problem.

***

**What Tythe Exposes**

Three on-chain primitives and one off-chain intelligence feed. Integrate one or all — they are composable by design.

1. **CEP (Credit Enhancement Profile):** Sovereign financial identity anchored on `did:cheqd`. Resolves any wallet to its verified owner, compliance status, and linked resources. The identity layer everything else builds on.
2. **TCT (Tokenized Creditworthiness):** Non-transferable ERC-20 character score (300-850). The primary credit signal for lending markets, exchanges, insurance protocols, and card issuers.

* **MVV (Maximum Vouchsafed Value):** Per-transaction enhancement ceiling in USD, embedded in TCT metadata. Caps value-based enhancements regardless of which signal the market reads. Sized at one-tenth of the participant's 30-day rolling credit capacity.
* **TIQ (Tokenized Investment Quality):** Investment quality score (300-850), embedded in TCT metadata. The primary credit signal for RWA platforms and yield vaults. Measures the reliability and performance of capital deployment across investment-oriented activity.
* **TLQ (Tokenized Liquidity Quality):** Liquidity quality score (300-850), embedded in TCT metadata. The primary credit signal for DEX pairs and LP markets. Measures the consistency and depth of liquidity provision behavior.

3. **CEW (Credit Enhancement Wrapper):** Smart contract proxy. Intercepts transactions, reads the configured signal (TCT, TIQ, or TLQ), and applies two independent credit adjustments — value-based and rate-based — automatically. Inherit CEW without re-architecting your stack.
4. **Relay Emitter:** Off-chain ML-powered nEvent feed. Classifies and labels negative credit events in real time and delivers structured, actionable signals to your systems.

***

**1. CEP (Identity Resolution)**

Call <mark style="color:red;">`resolveWallet(address wallet)`</mark> on the Attestation Registry. Returns the wallet's associated `did:cheqd` identifier and primary wallet address. Returns <mark style="color:red;">`("", address(0))`</mark> for any unlinked wallet (treat these as anonymous).

What resolution confirms:

* Verified KYC and sanctions status via zero-knowledge attestation
* Proof of Personhood confirmed human uniqueness
* Wallet-to-identity binding. Every linked address maps to one verified root DID

**Build to the DID, not the wallet address.** A participant's CEP persists across wallet rotations. The DID is the persistent identifier for a participant's credit state. No raw PII ever touches your protocol.

Additional read functions:

```solidity
isLinked(address wallet)    // true if wallet has a linked CEP
getTIQ(address wallet)      // TIQ score direct from Registry
getTLQ(address wallet)      // TLQ score direct from Registry
```

{% hint style="info" %}
**Use when:** Your protocol needs to verify a participant is a real, KYC-compliant individual before granting access to lending markets, RWA pools, permissioned vaults, stablecoin issuers.
{% endhint %}

***

**2. TCT, MVV, TIQ, TLQ (Credit Signals)**

All four signals are readable from the TCT Contract. One contract address, one integration.

```solidity
balanceOf(address wallet)           // TCT score (300-850)
getMVV(address wallet)              // MVV in USD, 18 decimals
getTIQ(address wallet)              // TIQ score (300-850)
getTLQ(address wallet)              // TLQ score (300-850)
getScoreBracket(address wallet)     // Bracket enum for TCT score
scoreToBracket(uint256 score)       // convert any raw score to Bracket enum
isEligible(address, uint256 minTCT) // true if TCT >= minTCT
isBlacklisted(address)              // true if wallet is blacklisted
```

**Signal selection by market type:**

<table><thead><tr><th width="100">Signal</th><th>Use When</th></tr></thead><tbody><tr><td>TCT</td><td>Lending markets, derivatives, exchanges, insurance, card issuers</td></tr><tr><td>TIQ</td><td>RWA platforms, yield vaults, structured credit</td></tr><tr><td>TLQ</td><td>DEX pairs, LP positions, liquidity management</td></tr><tr><td>MVV</td><td>Always available, caps value-based enhancements per transaction regardless of signal</td></tr></tbody></table>

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

* **MVV is a dollar ceiling, not a bracket score.** \
  It caps the dollar value of value-based enhancements per transaction. Transactions above MVV still proceed, enhancement only  applies up to MVV, the remainder at standard terms. MVV is sized by the scoring engine at one-tenth of the participant's 30-day rolling credit capacity. Never treat MVV as a block.
* **Read at transaction time, not session initiation.** \
  Scores update between transactions either positively via Manual Refresh or negatively via Auto-Slash. A cached value is stale the moment a score changes.

{% hint style="info" %}
**Use when:** Your protocol needs differentiated risk pricing (dynamic LTV, tiered interest rates, credit-aware vault thresholds, DEX fee structures, investment and liquidity quality scoring).
{% endhint %}

***

**3. CEW**

Inherit the CEW interface. Register your market via <mark style="color:red;">`registerMarket(address market, MarketConfig calldata config)`</mark>.

**MarketConfig fields:**

```solidity
struct MarketConfig {
    bool       isActive;
    // Value-based config (dollar amount adjustments, capped at MVV)
    uint256    valueBoostBps;       // max Enhancement on $ amounts (DAO ceiling: 700 = 7%)
    uint256    valueReductionBps;   // max Enforcement on $ amounts (DAO ceiling: 700 = 7%)
    bool       enforceValueAdj;     // false = no Enforcement for Fair/Poor on $ amounts
    // Rate-based config (interest rate adjustments, no MVV cap)
    uint256    rateBoostBps;        // max Enhancement on interest rates (DAO ceiling: 700 = 7%)
    uint256    rateReductionBps;    // max Enforcement on interest rates (DAO ceiling: 700 = 7%)
    bool       enforceRateAdj;      // false = no Enforcement for Fair/Poor on rates
    // Shared config
    bool       enforceBlock;        // true = block Flagged wallets
    address    feeToken;            // token used for Enhancement fee collection
    SignalType signalType;          // TCT, TIQ, or TLQ — one selection per market
}
```

Markets configure exactly one signal type. CEW reads that signal at transaction time and applies two independent adjustments. MVV is always read from the TCT contract regardless of signal type.

Call <mark style="color:red;">`getCreditAction(uint256 value)`</mark> from within your transaction logic to get a <mark style="color:red;">`CreditAction`</mark> without modifying state. <mark style="color:red;">`msg.sender`</mark> is the participant, <mark style="color:red;">`address(this)`</mark> is the market.

**CreditAction struct:**

```solidity
struct CreditAction {
    ActionType valueAction;     // action for dollar amount adjustments
    uint256    valueMagnitude;  // basis points, applied up to MVV
    uint256    mvvCeiling;      // MVV in USD, 18 decimals
    ActionType rateAction;      // action for interest rate adjustments
    uint256    rateMagnitude;   // basis points, no MVV cap
}
```

**Action types and bracket mapping — identical for both value and rate tracks:**

<table><thead><tr><th width="110">Bracket</th><th width="200">Action</th><th>Value Magnitude</th><th>Rate Magnitude</th></tr></thead><tbody><tr><td>Excellent</td><td>HighBoost if <mark style="color:red;"><code>valueBoostBps >= 600</code></mark> else LowBoost</td><td>valueBoostBps or valueBoostBps / 2</td><td>rateBoostBps or rateBoostBps / 2</td></tr><tr><td>Very Good</td><td>LowBoost</td><td>valueBoostBps / 2</td><td>rateBoostBps / 2</td></tr><tr><td>Good</td><td>Neutral</td><td>0</td><td>0</td></tr><tr><td>No Data</td><td>Neutral</td><td>0</td><td>0</td></tr><tr><td>Fair</td><td>HighReduction if <mark style="color:red;"><code>valueReductionBps >= 600</code></mark> else LowReduction</td><td>valueReductionBps or valueReductionBps / 2</td><td>rateReductionBps or rateReductionBps / 2</td></tr><tr><td>Poor</td><td>HighReduction</td><td>valueReductionBps</td><td>rateReductionBps</td></tr><tr><td>Flagged</td><td>Block if <mark style="color:red;"><code>enforceBlock = true</code></mark> else HighReduction</td><td>0 or valueReductionBps</td><td>0 or rateReductionBps</td></tr></tbody></table>

If <mark style="color:red;">`enforceValueAdj = false`</mark>, Fair and Poor return Neutral for the value track. If <mark style="color:red;">`enforceRateAdj = false`</mark>, Fair and Poor return Neutral for the rate track. Enforcement is optional — markets that do not want to penalize lower-reliability participants leave both enforcement flags false.

**On Block:** CEW returns <mark style="color:red;">`CreditAction`</mark> with Block on both tracks (does not revert). Your protocol must implement the revert in your own execution logic after reading the returned action type.

**Fee switch:** CEW launches fee-free. <mark style="color:red;">`feesActive`</mark> defaults to false. When the Tythe DAO activates fees, a flat 0.07% applies to all three action types; Enhancement fee paid by the participant on-chain at transaction time, Enforcement and Blocker fees tracked off-chain and invoiced monthly to your market.

{% hint style="info" %}
**Use when:** Your protocol wants automated, credit-differentiated execution without rebuilding core logic. For lending markets, derivatives & exchanges, RWA pools, DEX pairs, and card issuers.
{% endhint %}

***

**4. Relay Emitter**

Off-chain intelligence feed. Subscribe via the Tythe Developer Portal. Labels and percentile rankings delivered to your systems in real time.

**nEvent types and signal impact:**

<table><thead><tr><th width="125">Event</th><th>Trigger</th><th width="150">Signal Affected</th><th>Enforcement</th></tr></thead><tbody><tr><td>Liquidation</td><td>Collateral failure on integrated market</td><td>TCT</td><td>Auto-Slash, severity by percentile rank</td></tr><tr><td>Default</td><td>Loan not repaid within grace period</td><td>TCT</td><td>Auto-Slash, severity by percentile rank</td></tr><tr><td>Exploit</td><td>Verified protocol attack involvement</td><td>TCT</td><td>Blacklist, CEP revoked, TCT set to zero</td></tr><tr><td>Mercenary</td><td>Rapid liquidity withdrawal under stress</td><td>TCT, TLQ</td><td>Alert on TCT, Auto-Slash on TLQ by percentile rank</td></tr><tr><td>Informed</td><td>Patterned high-alpha toxic flow</td><td>TCT, TIQ</td><td>Alert on TCT, Auto-Slash on TIQ by percentile rank</td></tr><tr><td>Whale</td><td>Objectively large on-chain transaction</td><td>TIQ, TLQ</td><td>Alert only, metadata tag sent to integrated markets</td></tr></tbody></table>

Each label includes CEP ID, event typology, percentile rank within the label spectrum, TCT delta where applicable, and epoch timestamp for replay prevention.

{% hint style="info" %}
**Use when:** Your protocol needs early warning on counterparty credit deterioration. For lending markets, vault managers, derivatives & exchanges, RWA platforms, and institutional risk desks.
{% endhint %}

***

**Composable Stacks**

<table><thead><tr><th width="275">Use Case</th><th>Primitives</th></tr></thead><tbody><tr><td>Credit-aware lending market</td><td>CEP + TCT/MVV + CEW (SignalType.TCT)</td></tr><tr><td>Risk-managed vault</td><td>TCT/MVV + Relay Emitter</td></tr><tr><td>Permissioned RWA pool</td><td>CEP + TIQ + CEW (SignalType.TIQ) + Relay Emitter</td></tr><tr><td>DEX LP market</td><td>TLQ + CEW (SignalType.TLQ) + Relay Emitter</td></tr><tr><td>Card issuer</td><td>CEP + TCT/MVV + CEW (SignalType.TCT)</td></tr><tr><td>Institutional risk desk</td><td>Relay Emitter + TCT + TIQ + TLQ</td></tr><tr><td>Full-stack integration</td><td>CEP + TCT + MVV + CEW + Relay Emitter</td></tr></tbody></table>

***

**What's Coming**

**APIs and SDKs** _(Roadmap):_ REST APIs and language-specific SDKs for web2-native integration. Contact [dev@tythe.network](mailto:dev@tythe.network) if your stack requires API access ahead of the roadmap.

**Tythe DAO and TYT Token** _(V1.2):_ Vote on technical specifications, integration standards, and protocol upgrade paths.

**CEV Integration** _(V2):_ Integration hooks for protocols offering undercollateralized lending backed by LP capital.

**Credit Data Exchange** _(V3):_ Anonymized, user-consented credit data for model building and risk research.

**Agentic Credit** _(V3):_ AI agents access credit through the same primitives. No additional integration required.
{% endtab %}

{% tab title="Business Guide (For Institutions)" %}
This guide covers how on-chain institutions integrate Tythe's credit primitives to deploy smarter capital, reduce risk exposure, and build more competitive products.

***

**What Tythe Gives You**

Three on-chain primitives and one off-chain intelligence feed. Each addresses a specific capital efficiency or risk management problem.

<table><thead><tr><th width="137">Primitive</th><th>What It Is</th><th>The Problem It Solves</th></tr></thead><tbody><tr><td>CEP</td><td>Sovereign financial identity on <code>did:cheqd</code>. Resolves a complete financial profile without exposing raw data.</td><td>Anonymous counterparties. Compliance overhead.</td></tr><tr><td>TCT + MVV</td><td>Non-transferable ERC-20 score (300–850) with per-transaction enhancement ceiling.</td><td>Undifferentiated risk pricing. Capital locked behind worst-case assumptions.</td></tr><tr><td>CEW</td><td>Smart contract proxy applying TCT-based credit logic at transaction time.</td><td>Manual underwriting. Static rate structures. Reactive enforcement.</td></tr><tr><td>Relay Emitter</td><td>Off-chain ML-powered nEvent feed with real-time labels and percentile rankings.</td><td>Delayed default detection. Reactive risk management.</td></tr></tbody></table>

***

**The Capital Efficiency Case**

Every market today prices anonymous participants at the same worst-case rate. That is capital inefficiency by design, causing your market to leave revenue on the table from high-quality participants and absorb unnecessary risk from low-quality ones.

TCT and MVV make the distinction machine-readable, on-chain, and enforceable at the contract level. A participant with an Excellent TCT score and a $500K MVV is not the same counterparty as someone with no credit history and zero vouchsafed value.&#x20;

Tythe makes that difference actionable.

High-reliability participants get better terms; your protocol becomes more competitive. \
Low-reliability participants face tighter controls; default and liquidation exposure decreases. Both happen automatically, without manual underwriting, at the point of every transaction.

***

**The Compliance Case**

Verifying users today means handling raw PII, maintaining KYC infrastructure, and accepting ongoing data liability. Most protocols skip it entirely or expose themselves trying.

CEP integrates zk-KYC and privacy-preserving sanctions screening via [Billions](https://billions.network). Identity verification and OFAC/AML screening are processed entirely via zero-knowledge attestation. Your market receives a cryptographic pass/fail signal, never the underlying personal data.&#x20;

No KYC stack to build. No data liability to absorb. Compliance handled at the identity layer before a participant ever reaches your market.

***

**The Risk Management Case**

By the time most protocols detect credit deterioration, the damage is done. The Relay Emitter changes the timeline.

The moment a Liquidation, Default, Exploit, or Mercenary event is detected, a structured label reaches your risk systems in real time, before contagion spreads. Every label includes the CEP ID, event typology, severity percentile rank, TCT delta, and epoch timestamp. For institutions managing active exposure across multiple markets, receiving a Default signal at detection versus after the fact is the difference between proactive and reactive risk management.

***

**Use Cases by Institution Type**

* **DeFi Lending:** Dynamic LTV and interest rate tiers replace static rate tables. High-reliability borrowers access better rates while you retain competitive positioning without increasing default exposure. Low-reliability positions face automatic enforcement. No manual intervention required.
* **DeFi Yield:** Credit-aware entry thresholds and yield allocation. High-TCT depositors unlock enhanced yield tiers. Mercenary and toxic flow actors face automatic restrictions before they affect your pool.
* **DeFi Staking:** Participation thresholds and reward structures based on live creditworthiness. Reliable stakers access better terms. Low-reliability profiles face automatic constraints at the point of entry.
* **DeFi Insurance:** Dynamic premium and coverage limits applied at entry based on TCT and MVV. Reliable participants access lower premiums automatically. Pool solvency improves without manual underwriting.
* **Derivatives & Exchanges:** Differentiated fee structures, spreads, and position limits based on live creditworthiness. High-TCT traders access better execution. Counterparty risk is priced accurately at the point of every trade. Toxic flow and informed trading flagged by the Relay Emitter before it reaches your liquidity.
* **RWA Platforms:** Investor quality scoring for permissioned pools. TCT and MVV provide an objective, on-chain reliability measure that complements internal underwriting. CEP resolution handles compliance gating without data liability.
* **Stablecoin Issuers:** Mint limits and collateral requirements scaled to TCT and MVV at issuance. Counterparty risk managed without KYC-ing every user directly.
* **Card Issuers:** TCT and MVV provide the on-chain credit signal for dynamic credit limit assignment and spending controls. High-reliability cardholders access higher limits automatically. MVV sets the per-transaction enhancement ceiling, no manual underwriting required for limit decisions. CEP compliance verification satisfies KYC requirements at onboarding without handling raw cardholder data.
* **Prediction Markets:** Position size limits and fee structures calibrated to verified financial capacity. TCT flags high-risk behavioral patterns before they become default exposure. CEP's zk-KYC via Billions closes pseudonymous compliance gaps. The Relay Emitter surfaces suspicious trading patterns and toxic flow in real time.

***

**Recommended Integration Stack**

<table><thead><tr><th width="177">Institution</th><th>CEP</th><th>TCT + MVV</th><th>CEW</th><th>Relay Emitter</th></tr></thead><tbody><tr><td><strong>DeFi Lending</strong></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td><strong>DeFi Yield</strong></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td><strong>DeFi Staking</strong></td><td>✓</td><td>✓</td><td>✓</td><td>Optional</td></tr><tr><td><strong>DeFi Insurance</strong></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td><strong>Derivatives &#x26; Exchanges</strong></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td><strong>RWA Platforms</strong></td><td>✓</td><td>✓</td><td>Optional</td><td>✓</td></tr><tr><td><strong>Stablecoin Issuers</strong></td><td>✓</td><td>✓</td><td>✓</td><td>Optional</td></tr><tr><td><strong>Card Issuers</strong></td><td>✓</td><td>✓</td><td>✓</td><td>Optional</td></tr><tr><td><strong>Prediction Markets</strong></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr></tbody></table>

***

**What's Coming**

**APIs & SDKs** _(Roadmap):_ REST APIs and SDKs for web2-native integration. Contact [business@tythe.network](mailto:business@tythe.network) for API access ahead of the roadmap.

**Tythe DAO & TYT Token** _(V1.2):_ Institutional DAO members vote on scoring formula parameters and protocol upgrades. Institutional members are the only participants with visibility into exact formula weights.

**Credit Enhancement Vaults** _(V2):_ The only module enabling undercollateralized lending on Tythe. Risk distributed across LPs who opt in explicitly. Institutions never absorb default risk they did not underwrite.

**Credit Data Licensing** _(V2):_ Anonymized, user-consented credit data in structured formats for risk modeling, research, and AI training.

**Agentic Credit** _(V2):_ High-reputation AI agents with verified execution history access credit through the same stack. Institutions integrated today automatically serve a new class of creditworthy counterparty. No additional integration required.
{% endtab %}
{% endtabs %}

