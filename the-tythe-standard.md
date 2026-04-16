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

# The Tythe Standard

## The Tythe Credit Enhancement Standard (TCE-26)

The Tythe Credit Enhancement (TCE) standard is the protocol's canonical framework for scoring and tokenizing creditworthiness. It defines how raw behavioral telemetry and decisional signals are transformed into Tokenized Creditworthiness (TCT); a machine-enforceable, real-time financial risk signal.

Creditworthiness in Tythe is established through a three-layer sovereign risk engine. Each layer has a distinct role: the Gate (Compliance) determines eligibility, the Metric (Credibility) determines the band, and the Multiplier (Capacity) determines the position within it.

***

#### I. The Gate (Compliance)

**Role:** Non-weighted prerequisite. The scoring engine remains dormant until the individual's Compliance Eligibility conditions have been met. No TCT token can be minted or refreshed without a verified Compliance Gate, regardless of on-chain activity.

The Gate operates in two tiers: mandatory requirements that unlock protocol access, and optional enhancements that strengthen a participant's profile.

**Mandatory (Protocol Access Requirements)**

The following steps are required to mint a `did:cheqd` identifier. Successful DID creation is the green light for protocol participation.

* **zk-KYC via Billions ID:** Identity verification and sanctions screening (OFAC/AML) processed via zero-knowledge attestation. No raw identity data is held by the protocol at any point.
* **Primary Wallet Address:** A verified primary wallet must be bound to the DID at registration. V1 launches with native Base and EVM support; additional EVM, SVM, and Move wallet support will be added alongside protocol growth.

**Optional (Credit Profile Enhancements)**

The following are not required for protocol access but positively affect a participant's TCT score.

* **Proof of Personhood (PoP):** Biometric-anchored Sybil resistance via World ID. Attaching a verified PoP credential grants a fixed **+5 TCT boost** to the participant's score.
* **Additional Wallet Connections:** Participants may connect multiple active wallet addresses to their CEP. Multi-wallet connectivity is treated as a positive behavioral signal, reflecting responsible on-chain security practices and genuine protocol engagement. This signal is captured within the Action Integrity input of the Reliability Score.

> **Protocol Note:** If a participant's compliance status is revoked post-mint, their TCT is immediately frozen and flagged. Reinstatement (which is usually accompanied by a TCT penalty) requires re-verification through the Compliance Gate.

***

#### II. The Metric (Credibility)

**Role:** Primary creditworthiness signal. Determines the participant's TCT band (300–850).

**Core Principle:** Credibility is the definitive measure of on-chain character. Capital cannot purchase entry into a higher band. It can only optimize a position within the band that behavior has earned. Tythe scores character first, capacity second.

The Credibility Score is calculated as a weighted aggregate across two tiers of behavioral inputs.

**Tier 1: Primary Drivers (80%)**

| Input                              | Weight | What It Measures                                                                                                            |
| ---------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------- |
| Historical Performance             | 35%    | Successful loan fulfillment over a 24-month window. Defaults carry a heavy decay factor. The longest memory in the formula. |
| Current Risk (Liquidation-at-Risk) | 20%    | Aggregate liabilities across all mapped wallets against real-time collateral values. Captures live solvency exposure.       |
| Credit Utilization                 | 15%    | Delta between current LTV and maximum permitted LTV. High edge-behavior is penalized in real time.                          |
| New Credit                         | 10%    | Frequency of debt acquisition. Detects financial distress or predatory borrowing patterns.                                  |

**Tier 2: Secondary Signals (20%)**

| Input               | Weight | What It Measures                                                                                                              |
| ------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------- |
| Volatility Quotient | 6%     | Penalizes over-exposure to low-liquidity or high-volatility assets. Calibrated directly by the CAVB.                          |
| Credit Mix          | 5%     | Rewards sophistication — interaction with complex vaults, LP management, and blue-chip protocols.                             |
| Investor Status     | 5%     | Quality of capital deployment on RWA platforms (Centrifuge, Maple, etc.). Holding qualifies; active management scores higher. |
| Action Integrity    | 4%     | Staking duration and protocol stickiness. Rewards committed, non-mercenary participation.                                     |

{% hint style="info" %}
#### **Parameter Note**

The 24-month historical window and tier weights are fixed at launch under TCE-26. Adjustments to these parameters require a successful governance proposal to the Tythe DAO, available in V1.2.
{% endhint %}

**The Relative Rank Rule:** Reaching the Excellent bracket (800–850) requires a participant's Behavioral Credibility to be mathematically in the top 10% of all scored participants. Capital capacity cannot bridge a reliability gap. It can only maximize the score within the band that behavior has already earned.

***

#### III. The Multiplier (Capacity)

**Role:** Determines a participant's position within their credibility band and underwrites the Maximum Vouchsafed Value (MVV).

Once the credibility band is set, Capital Capacity acts as a scale multiplier that pushes the score toward the ceiling of the bracket and determining how much credit the protocol is willing to vouchsafe for the position.

**Examples:**

<table><thead><tr><th width="200">Profile</th><th>Credibility</th><th>Capacity</th><th>TCT Output</th></tr></thead><tbody><tr><td>Retail, High Credibility</td><td>Top 10% behavior</td><td>Low capacity</td><td>803 (Excellent band, lower MVV)</td></tr><tr><td>Whale, High Credibility</td><td>Top 10% behavior</td><td>High capacity</td><td>849 (Excellent band, maximum MVV)</td></tr><tr><td>Whale, Mid Credibility</td><td>60th percentile</td><td>High capacity</td><td>739 (Capped at Good band ceiling)</td></tr></tbody></table>

**Capacity Input Markers:**

* **Aggregate Net Worth:** Real-time TVL across all mapped addresses.
* **LP & Staking Depth:** Size and duration of provided DEX liquidity.
* **Verified Cashflow:** Recurring on-chain rewards or zkTLS-verified off-chain income.
* **Transactional Weight:** Average transaction size distinguishes heavyweight participants from retail activity.

**Maximum Vouchsafed Value (MVV):** Capacity dictates a participant's dollar credit limit. A CEW boost is only applied up to the verified MVV; ensuring the protocol never over-extends its vouchsafe beyond a participant's proven capital surface.

***

#### The Collateral Asset Volatility Benchmark (CAVB)

The CAVB governs two things: the **Volatility Quotient** component of the Credibility Score, and the **MVV ceiling**. Collateral quality affects both how the protocol scores participant behavior and how much it is willing to vouchsafe against a given position.

<table><thead><tr><th width="180">Class</th><th width="250">Standard</th><th width="155">Scoring Impact</th><th>MVV Impact</th></tr></thead><tbody><tr><td>AAA (Pristine)</td><td>Major stables, tokenized gold, T-bills, money market funds</td><td>Positive</td><td>Full MVV eligible</td></tr><tr><td>AA (Blue-Chip)</td><td>BTC, ETH and LSTs, short-term tokenized treasuries</td><td>Neutral-Positive</td><td>Full MVV eligible</td></tr><tr><td>A (Top Alternatives)</td><td>Top 3–40 CMC, tokenized stocks/ETFs</td><td>Neutral</td><td>Slightly discounted MVV</td></tr><tr><td>BBB (Hard Assets)</td><td>Top 41–100 CMC, tokenized private credit</td><td>Neutral</td><td>Discounted MVV</td></tr><tr><td>BB (High Retail)</td><td>Top 101–150 CMC, mid memes, tokenized real estate</td><td>Neutral</td><td>Moderately discounted MVV</td></tr><tr><td>B (Speculative)</td><td>Top 151–300 CMC, tokenized physical assets</td><td>Neutral</td><td>Heavily discounted MVV</td></tr><tr><td>CCC (Junk)</td><td>All other assets</td><td>Negative </td><td>Excluded from MVV</td></tr></tbody></table>

{% hint style="info" %}
#### **Design Note**

Asset classes below AA are not penalized in scoring; individual participants are not punished for holding them. However, the protocol applies progressively heavier MVV discounts against these positions. CCC assets actively hurt the Reliability Score and carry zero vouchsafe power.
{% endhint %}

***

#### The TCT Lifecycle

Tythe uses a unified registry of EIP-712 attestations to coordinate credit truth across all integrated markets.

**Manual Refresh for Positive Growth (Participant-Initiated):** Participants control when to refresh their score for positive changes. The Tythe backend generates a signed EIP-712 attestation, which the participant anchors to their on-chain TCT balance and MVV limit via the dashboard. All gas costs for manual updates are borne by the participant.

**Auto-Slash for Negative Enforcement (Protocol-Initiated):** When a critical nEvent is detected and classified by the Relay Emitter, the protocol bypasses the participant and immediately updates the on-chain TCT balance. Slash severity is determined by the individual's percentile rank within their label's spectrum. Auto-slashes are gasless; enforcement is protocol-side.

***

#### Negative Event Typology (nEvents)

The Relay Emitter is an ML-powered intelligence layer built on gradient boosting models (XGBoost and LightGBM); not a blockchain feature. It continuously monitors on-chain behavioral patterns, classifies negative credit events into labeled categories, and ranks each individual within their label's spectrum by severity relative to others in the same category. These rankings are distributed through two channels:

* **Externally:** Delivered to institutional subscribers as real-time risk intelligence via tiered subscription feeds. Institutions use this signal for independent risk management and capital decisions.
* **Internally:** Consumed by Tythe's own deterministic scoring engine to trigger Auto-Slash enforcement with proportional severity.

The Relay Emitter classifies and ranks. The deterministic formula scores. These are distinct functions; the Relay Emitter never makes credit decisions directly.

nEvent labels are attached to the acting entity's CEP ID. Where applicable, they trigger the corresponding on-chain enforcement response.

| Event       | Nature                                                     | Enforcement                                                     |
| ----------- | ---------------------------------------------------------- | --------------------------------------------------------------- |
| Liquidation | Collateral failure on an integrated market                 | Auto-Slash; severity determined by percentile rank within label |
| Default     | Failure to fulfill debt within grace period                | Auto-Slash; severity determined by percentile rank within label |
| Exploit     | Verified involvement in smart contract or protocol attacks | Blacklist; CEP revoked, TCT set to zero                         |
| Mercenary   | Rapid liquidity withdrawal during systemic stress          | Alert Only                                                      |
| Informed    | Patterned high-alpha trades indicating toxic arbitrage     | Alert Only                                                      |
| Whale       | Objectively large on-chain transactions or transfers       | Alert Only                                                      |

**Standard Fields on Every nEvent Label:**

* **CEP ID:** The sovereign identifier associated with the event.
* **Event Typology:** The specific nature of the credit movement.
* **Percentile Rank:** The individual's position within their label's spectrum relative to all others in the same category.
* **TCT Delta:** The precise numerical change to the TCT balance, where applicable.
* **Epoch Timestamp:** Cryptographic sequencing to prevent replay attacks.<br>

**Percentile-Based Slash Severity**

The Relay Emitter's percentile ranking within each nEvent label determines the severity of the on-chain TCT reduction. The translation from percentile rank to slash severity is defined by a protocol-governed lookup table. The exact parameters are sealed under DAO license and modifiable only via a successful governance proposal with a mandatory timelock.

***

#### Risk Brackets

The Credit Enhancement Wrapper (CEW) translates a participant's TCT balance into standardized economic actions across all integrated markets.

{% hint style="info" %}
#### CEW Action Key

<mark style="color:$success;">Enhancement</mark> = Positive Boost\
<mark style="color:$warning;">Enforcement</mark> = Negative Adjustment\
<mark style="color:$danger;">Block</mark> = Hard Deny
{% endhint %}

| Range   | Bracket   | CEW Action                                                   |
| ------- | --------- | ------------------------------------------------------------ |
| 800–850 | Excellent | <mark style="color:$success;">Enhancement</mark> (High)      |
| 740–799 | Very Good | <mark style="color:$success;">Enhancement</mark> (Low)       |
| 670–739 | Good      | <mark style="color:$primary;">Risk Neutral</mark>; No Change |
| 580–669 | Fair      | <mark style="color:$warning;">Enforcement</mark> (Low)       |
| 300–579 | Poor      | <mark style="color:$warning;">Enforcement</mark> (High)      |
| 1       | No Data   | <mark style="color:$info;">Credit Invisible</mark>           |
| 0       | Flagged   | <mark style="color:$danger;">Blocked</mark>                  |

***

#### Transparency & Open Source Commitment

Tythe operates a three-tier transparency model, balancing public trust with formula integrity.

* **Smart Contract Code:** Fully open source. Auditable by anyone, always. Non-negotiable.
* **Formula Structure:** Public. Category names, tier hierarchy, and percentage weights are disclosed so all participants understand what drives the score.
* **Exact Parameters & Weights:** Sealed under a DAO license. Visible only to institutional DAO members. Modifications require a successful governance proposal with a mandatory timelock. This prevents gaming without sacrificing accountability.

***

#### The Evolving Standard

TCE-26 is the protocol's launch model. As Tythe matures, new telemetry streams will be integrated into scoring; including zk-verified bank statements, payroll and tax data, cross-chain bridging history, encrypted imports of FICO, CIBIL, and other centralized credit scores, and expanded verifiable credential checks via zkTLS.

This ensures TCT becomes increasingly inclusive, allowing participants with limited on-chain history but strong off-chain reliability to access on-chain capital over time.

Future models (TCE-27 and beyond) will be designed in response to market shifts and activated only via a successful Tythe DAO governance proposal.

***

#### FAQs

<details>

<summary><strong>Why should we trust Tythe's TCT score?</strong></summary>

Unlike legacy credit scores, TCT is built on determinism. Every score update is backed by a verifiable on-chain event or a cryptographic zk-proof. The smart contract code is fully open source. The formula structure is publicly disclosed. The signal is objective, auditable, and resistant to manipulation.

</details>

<details>

<summary><strong>Does Tythe have the authority to freeze funds?</strong></summary>

No. Tythe is a neutral risk-intelligence layer, not a custodian. The protocol can slash TCT balances based on verified behavioral events. Lenders and integrated markets make their own independent decisions on whether to adjust or restrict participant positions based on Tythe's signals.

</details>

<details>

<summary><strong>How does Tythe prevent Sybil attacks?</strong></summary>

Credit is bound to the CEP ID, which requires a unique zk-KYC verification and Proof of Personhood. A participant may control multiple wallets — but all wallets map to a single root identity. Credit power cannot be artificially multiplied across fake accounts.

</details>

<details>

<summary><strong>What happens if a participant is wrongly slashed?</strong></summary>

Disputed slashes are handled by the Justice Arm of the Tythe DAO. AI clerks prepare evidence briefs from on-chain data. A human jury — drawn from the same TCT band as the disputant — reviews the case and delivers a verdict. Disputes at band boundaries are heard by mixed juries from both adjacent bands.

</details>

