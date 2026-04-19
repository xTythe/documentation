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

The TCE (Tythe Credit Enhancement) standard defines how on-chain behavioral data is transformed into four verifiable, machine-enforceable credit signals: TCT, MVV, TIQ, and TLQ. Each signal serves a distinct function across integrated markets. All four are computed off-chain by the scoring engine, signed via EIP-712 attestation, and anchored on-chain by the participant at Refresh.

***

#### Compliance

The Compliance Gate is a non-weighted prerequisite. The scoring engine remains dormant until compliance conditions are met. No TCT token can be minted or refreshed without a verified Compliance Gate, regardless of on-chain activity.

**Mandatory**

* **zk-KYC via Billions:** Identity verification and sanctions screening (OFAC/AML) processed via zero-knowledge attestation. No raw identity data is held by the protocol at any point.
* **Primary Wallet:** A verified primary wallet must be bound to the DID at registration. V1 launches with native Base and EVM support. Additional EVM, SVM, and Move wallet support added alongside protocol growth.

**Optional**

* **Proof of Personhood (PoP):** Biometric-anchored Sybil resistance via World ID. Grants a fixed **+5 TCT boost** and strengthens profile Sybil resistance.
* **Additional Wallets:** Multi-wallet connectivity signals responsible on-chain security practices. Captured within the Action Integrity input.

Once mandatory conditions are met, a `did:cheqd` identifier is minted. This is the green light for protocol participation.

{% hint style="warning" %}
**Protocol Note:** If a participant's compliance status is revoked post-mint, their TCT is immediately frozen and flagged. Reinstatement (which is usually accompanied by a TCT penalty) requires re-verification through the Compliance Gate.
{% endhint %}

***

#### Scores & Limits

<details>

<summary><strong>TCT: Tokenized Creditworthiness</strong> </summary>

**Tokenized Creditworthiness.** A non-transferable ERC-20 token scored 300 to 850. TCT is a pure character signal earned through seven behavioral inputs and lost through verified negative events. It represents the reliability and consistency of a participant's on-chain credit behavior over time.

TCT governs CEW actions across lending markets, derivatives, exchanges, insurance protocols, and card issuers.

**Scoring Inputs**

<table><thead><tr><th width="200">Input</th><th width="100">Weight</th><th>What It Measures</th></tr></thead><tbody><tr><td>Historical Performance</td><td>35%</td><td>Successful loan fulfillment over a 24-month window. Defaults carry a heavy decay factor. The longest memory in the formula.</td></tr><tr><td>Current Risk (LaR)</td><td>20%</td><td>Aggregate liabilities across all mapped wallets against real-time collateral values. Captures live solvency exposure.</td></tr><tr><td>Credit Utilization</td><td>15%</td><td>Delta between current LTV and maximum permitted LTV. High edge-behavior is penalized in real time.</td></tr><tr><td>New Credit</td><td>10%</td><td>Frequency of debt acquisition. Detects financial distress or predatory borrowing patterns.</td></tr><tr><td>Volatility Quotient</td><td>9%</td><td>Penalizes over-exposure to low-liquidity or high-volatility assets. Calibrated directly by the CAQB.</td></tr><tr><td>Credit Mix</td><td>6%</td><td>Rewards sophistication; interaction with complex vaults, LP management, and blue-chip protocols.</td></tr><tr><td>Action Integrity</td><td>5%</td><td>Staking duration and protocol stickiness. Rewards committed, non-mercenary participation.</td></tr></tbody></table>

{% hint style="info" %}
The 24-month historical window and tier weights are fixed at launch under TCE-26. Adjustments require a successful governance proposal to the Tythe DAO in V1.2.
{% endhint %}

</details>

<details>

<summary><strong>TIQ: Tokenized Investor Quality</strong> </summary>

**Tokenized Investment Quality.** A metadata value scored 300 to 850, embedded in the TCT token alongside TCT and MVV. TIQ measures the quality of a participant's capital deployment across investment-oriented activity such as RWA platforms, yield vaults, and structured credit positions.

TIQ governs CEW actions on RWA platforms and yield vaults where investment quality is the primary risk signal.

**Scoring Inputs**

| Input                | Priority  |
| -------------------- | --------- |
| Investor Status      | Primary   |
| Net Worth            | Secondary |
| Verified Cashflow    | Secondary |
| Transactional Weight | Secondary |

TIQ excludes LP depth. Liquidity provision is captured separately by TLQ.

</details>

<details>

<summary><strong>TLQ: Tokenized Liquidity Quality</strong></summary>

**Tokenized Liquidity Quality.** A metadata value scored 300 to 850, embedded in the TCT token alongside TCT and MVV. TLQ measures the quality of a participant's liquidity provision behavior across DEX pairs, LP positions, and liquidity management across markets.

TLQ governs CEW actions on DEX pairs and LP-related markets where liquidity quality is the primary risk signal.

**Scoring Inputs**

| Input                | Priority  |
| -------------------- | --------- |
| LP Depth             | Primary   |
| Net Worth            | Secondary |
| Verified Cashflow    | Secondary |
| Transactional Weight | Secondary |

TLQ excludes Investor Status. Investment activity is captured separately by TIQ.

</details>

<details>

<summary><strong>MVV: Maximum Vouchsafed Value</strong> </summary>

**Maximum Vouchsafed Value.** A metadata value embedded in the TCT token. MVV is the protocol's assessed per-transaction credit ceiling for lending and collateral markets. CEW Enhancement is applied up to MVV. Transactions above MVV proceed at standard terms for the remainder.

MVV is not a depleting credit line. It is a per-transaction ceiling that reflects a participant's capital capacity at the time of their last Refresh.

**Scoring Inputs**

| Input                | What It Measures                                              |
| -------------------- | ------------------------------------------------------------- |
| Net Worth            | Real-time TVL across all mapped addresses                     |
| LP Depth             | Size and duration of provided DEX liquidity                   |
| Investor Status      | Quality of capital deployment on RWA platforms                |
| Verified Cashflow    | Recurring on-chain rewards or zkTLS-verified off-chain income |
| Transactional Weight | Average transaction size                                      |

MVV ceiling is further governed by the CAQB. Collateral asset quality directly affects how much the protocol is willing to vouchsafe against a given position.

</details>

***

#### Benchmarks

<details>

<summary><strong>CAQB: Collateral Asset Quality Benchmark</strong></summary>

**Collateral Asset Quality Benchmark.** A risk-weighting index that categorizes collateral assets from AAA (Pristine) to CCC (Junk) based on 180-day realized volatility and secondary market depth. The CAQB governs the Volatility Quotient input in TCT scoring and the ceiling calculations for MVV.

<table><thead><tr><th width="90">Class</th><th>Standard</th><th width="150">Scoring Impact</th><th>MVV Ceiling Impact</th></tr></thead><tbody><tr><td>AAA</td><td>Major stables, tokenized gold, T-bills, money market funds</td><td>Positive</td><td>Full ceiling eligible</td></tr><tr><td>AA</td><td>BTC, ETH and LSTs, short-term tokenized treasuries</td><td>Neutral-Positive</td><td>Full ceiling eligible</td></tr><tr><td>A</td><td>Top 3-40 CMC, tokenized stocks/ETFs</td><td>Neutral</td><td>Slightly discounted</td></tr><tr><td>BBB </td><td>Top 41-100 CMC, tokenized private credit</td><td>Neutral</td><td>Discounted</td></tr><tr><td>BB</td><td>Top 101-150 CMC, mid memes, tokenized real estate</td><td>Neutral</td><td>Moderately discounted</td></tr><tr><td>B </td><td>Top 151-300 CMC, tokenized physical assets</td><td>Neutral</td><td>Heavily discounted</td></tr><tr><td>CCC</td><td>All other assets</td><td>Negative</td><td>Excluded</td></tr></tbody></table>

{% hint style="info" %}
Asset classes below AA are not penalized in TCT scoring. The protocol applies progressively heavier MVV discounts against these positions. CCC assets actively hurt the Volatility Quotient subscore and carry zero MVV power.
{% endhint %}

</details>

<details>

<summary><strong>IAQB: Investor Asset Quality Benchmark</strong></summary>

Governs the TIQ ceiling. Categorizes assets by reliability as investment vehicles. Primary criteria are yield reliability, institutional legitimacy, underlying asset quality, and exit liquidity.

<table><thead><tr><th width="90">Class</th><th>Standard</th><th>Rationale</th></tr></thead><tbody><tr><td>AAA</td><td>Tokenized T-bills, money market funds, tokenized gold, USDC/USDT/DAI/USDe in yield strategies</td><td>Government-backed or hard asset backed. Most institutionally recognized stablecoins. Reliable, verifiable yield.</td></tr><tr><td>AA</td><td>Tokenized investment-grade corporate bonds, major stablecoins with regular audits outside the top four, BTC/ETH in yield vaults</td><td>Strong underlying credit quality. Verifiable yield. High institutional recognition.</td></tr><tr><td>A</td><td>Tokenized prime real estate, Centrifuge/Maple senior tranches, tokenized ETFs, tokenized short-term treasuries</td><td>Real asset backing with verifiable yield. Some illiquidity risk.</td></tr><tr><td>BBB</td><td>Tokenized private credit (senior), RWA platform junior tranches, algorithmic stablecoins with proven track records and meaningful TVL</td><td>Higher yield, higher risk. Still defensible institutional quality.</td></tr><tr><td>BB</td><td>Tokenized physical assets, tokenized emerging market debt, mid-tier RWA platforms, top 1-40 CMC tokens in yield strategies</td><td>Meaningful credit risk. Yield less reliable. Limited institutional recognition.</td></tr><tr><td>B</td><td>Speculative RWA structures, top 41-100 CMC tokens in yield strategies</td><td>High volatility underlying. Yield unreliable. Minimal institutional backing.</td></tr><tr><td>CCC</td><td>Unaudited or experimental stablecoins, stablecoins with opaque backing or prior depeg history, all other assets</td><td>No institutional recognition. Yield unverifiable or non-existent.</td></tr></tbody></table>

***

</details>

<details>

<summary><strong>LAQB: Liquidity Asset Quality Benchmark</strong></summary>

Governs the TLQ ceiling. Categorizes assets by reliability as liquidity pair constituents — primary criteria are trading volume depth, impermanent loss risk, market depth, and pair legitimacy.

<table><thead><tr><th width="90">Class</th><th>Standard</th><th>Rationale</th></tr></thead><tbody><tr><td>AAA</td><td>USDC/USDT, USDC/DAI, USDC/USDe, major stablecoin pairs</td><td>Near-zero impermanent loss. Consistent fee income. Maximum depth.</td></tr><tr><td>AA</td><td>ETH/USDC, BTC/USDC, ETH/BTC, LST/ETH pairs</td><td>Blue-chip pairs with deep liquidity. Low impermanent loss relative to volume.</td></tr><tr><td>A</td><td>Top 3-20 CMC token pairs with major stablecoins or ETH/BTC</td><td>High volume. Meaningful impermanent loss risk but offset by fee income.</td></tr><tr><td>BBB</td><td>Top 21-40 CMC token pairs, tokenized asset pairs with major stablecoins</td><td>Moderate depth. Impermanent loss risk elevated. Fees can compensate.</td></tr><tr><td>BB</td><td>Top 41-100 CMC token pairs, mid-tier tokenized asset pairs</td><td>Thinner depth. Higher impermanent loss. Fee income less reliable.</td></tr><tr><td>B</td><td>Top 101-300 CMC token pairs, speculative tokenized asset pairs</td><td>Low depth. High impermanent loss risk. Fee income unreliable.</td></tr><tr><td>CCC</td><td>All other pairs, manufactured liquidity pools, pairs with no verifiable organic volume</td><td>No genuine market depth. Fee income non-existent or artificial.</td></tr></tbody></table>

</details>

***

#### Credit Events

<details>

<summary><strong>nEvents: Negative Events</strong></summary>

**Negative Events.** Verifiable on-chain credit deterioration events detected, classified, and ranked by the Relay Emitter. nEvents trigger Auto-Slash enforcement on the relevant signal. Slash severity is determined by the participant's percentile rank within their label's spectrum.

Each nEvent label includes:&#x20;

* CEP ID
* Event typology
* Percentile rank
* TCT delta (where applicable)
* Epoch timestamp for replay prevention

**nEvent Typology and Signal Impact**

<table><thead><tr><th width="120">Event</th><th>Nature</th><th width="150">Signal Affected</th><th>Enforcement</th></tr></thead><tbody><tr><td>Liquidation</td><td>Collateral failure on an integrated market</td><td>TCT</td><td>Auto-Slash (severity by percentile rank)</td></tr><tr><td>Default</td><td>Failure to fulfill debt within grace period</td><td>TCT</td><td>Auto-Slash (severity by percentile rank)</td></tr><tr><td>Exploit</td><td>Verified involvement in smart contract attacks</td><td>TCT</td><td>Blacklist (CEP revoked, TCT set to 0)</td></tr><tr><td>Mercenary</td><td>Rapid liquidity withdrawal during systemic stress</td><td>TCT, TLQ</td><td>Alert on TCT (Auto-Slash on TLQ by percentile rank)</td></tr><tr><td>Informed</td><td>Patterned high-alpha trades indicating toxic arbitrage</td><td>TCT, TIQ</td><td>Alert on TCT (Auto-Slash on TIQ by percentile rank)</td></tr><tr><td>Whale</td><td>Objectively large on-chain transactions</td><td>TIQ, TLQ</td><td>Alert only (metadata tag sent to integrated markets)</td></tr></tbody></table>

{% hint style="info" %}
MVV is not directly slashed by nEvents. MVV updates only via Manual Refresh. A TCT slash may reduce a participant's scored capacity inputs at next Refresh, resulting in a lower MVV on the next update.
{% endhint %}

</details>

***

#### Risk Brackets

TCT, TIQ, and TLQ all use the same bracket scale and the same CEW action mapping. Markets configure which signal CEW reads at registration. The bracket logic is identical regardless of signal type.

{% hint style="info" %}
**CEW Action Key**

* <mark style="color:$success;">Enhancement</mark> = Positive Boost
* <mark style="color:$warning;">Enforcement</mark> = Negative Adjustment
* &#x20;<mark style="color:$danger;">Block</mark> = Hard Deny
{% endhint %}

| Range   | Bracket   | CEW Action                                              |
| ------- | --------- | ------------------------------------------------------- |
| 800-850 | Excellent | <mark style="color:$success;">Enhancement</mark> (High) |
| 740-799 | Very Good | <mark style="color:$success;">Enhancement</mark> (Low)  |
| 670-739 | Good      | <mark style="color:$primary;">Neutral</mark>            |
| 580-669 | Fair      | <mark style="color:$warning;">Enforcement</mark> (Low)  |
| 300-579 | Poor      | <mark style="color:$warning;">Enforcement</mark> (High) |
| 1       | No Data   | <mark style="color:$info;">Credit Invisible</mark>      |
| 0       | Slashed   | <mark style="color:$danger;">Blocked</mark>             |

Enhancement and Enforcement magnitudes are market-configured within DAO-governed bounds. Markets set their own discount rates per bracket within the allowed range. Enforcement is optional, markets may leave Fair and Poor brackets at Neutral if their risk model does not require negative adjustment beyond current provided rates.

***

#### Open Source Commitment

Tythe operates a three-tier transparency model, balancing public trust with formula integrity.

1. **Smart Contract Code:** Fully open source. Auditable by anyone, always. Non-negotiable.
2. **Formula Structure:** Public. Category names, tier hierarchy, and percentage weights are disclosed so all participants understand what drives their score.
3. **Exact Parameters and Weights:** Sealed under a DAO license. Visible only to institutional DAO members. Modifications require a successful governance proposal with a mandatory timelock. This prevents gaming without sacrificing accountability.

***

#### The Evolving Standard

TCE-26 (Tythe Credit Enhancement, 2026) is the protocol's launch model. As Tythe matures, new telemetry streams will be integrated into scoring, including zk-verified bank statements, payroll and tax data, cross-chain bridging history, encrypted imports of FICO, CIBIL, and other centralized credit scores, and expanded verifiable credential checks via zkTLS.

Future models (TCE-27 and beyond) are activated only via a successful Tythe DAO governance proposal. No scoring change takes effect without community oversight and a mandatory timelock.

***

#### FAQs

**1. Why should we trust Tythe's TCT score?**\
TCT is built on determinism. Every score update is backed by a verifiable on-chain event or a cryptographic zk-proof. The smart contract code is fully open source. The formula structure is publicly disclosed. The signal is objective, auditable, and resistant to manipulation.

**2. Does Tythe have the authority to freeze funds?**\
No. Tythe is a neutral risk-intelligence layer, not a custodian. The protocol can slash TCT balances based on verified behavioral events. Integrated markets make their own independent decisions on whether to adjust or restrict participant positions based on Tythe's signals.

**3. How does Tythe prevent Sybil attacks?**\
Credit is bound to the CEP ID, which requires a unique zk-KYC verification and Proof of Personhood. A participant may control multiple wallets but all wallets map to a single root identity. Credit power cannot be artificially multiplied across fake accounts.

**4. What happens if a participant is wrongly slashed?**\
Disputed slashes are handled by the Justice Arm of the Tythe DAO. AI clerks prepare evidence briefs from on-chain data. A human jury drawn from the same TCT band as the disputant reviews the case and delivers a verdict. Disputes at band boundaries are heard by mixed juries from both adjacent bands. To raise a dispute, participants stake a protocol-defined amount of TCT as a good faith deposit. The stake is burned if the slash is upheld and returned in full if overturned.

**5. What is the difference between TCT, TIQ, and TLQ?**\
TCT measures on-chain credit character — borrowing behavior, repayment history, and risk management. It is the primary signal for lending markets, derivatives, exchanges, insurance protocols, and card issuers. TIQ measures investment quality — the reliability and performance of capital deployed across RWA platforms and yield vaults. TLQ measures liquidity quality — the consistency and depth of liquidity provision across DEX pairs and LP positions. All three use the same 300-850 bracket scale and the same CEW action mapping. Markets configure which signal CEW reads at registration.

**6. Can a market read more than one score signal simultaneously?**\
No. Each integrated market configures CEW to read exactly one score signal (TCT, TIQ, or TLQ) at registration. MVV limit signal is independent and always available regardless of which score signal the market reads. This keeps the integration clean and the credit logic unambiguous.

**7. Which nEvents affect which signals?**\
Liquidation, Default, and Exploit affect TCT only. Mercenary events affect both TCT (alert) and TLQ (Auto-Slash). Informed events affect both TCT (alert) and TIQ (Auto-Slash). Whale events affect TIQ and TLQ as alerts only. MVV is never directly slashed by nEvents, it updates only at Manual Refresh.

**8. What are CAQB, IAQB, and LAQB?**\
Three asset quality benchmarks that govern the ceiling calculations for MVV, TIQ, and TLQ respectively. CAQB (Collateral Asset Quality Benchmark) categorizes assets by reliability as collateral backing and governs the MVV ceiling and Volatility Quotient input. IAQB (Investor Asset Quality Benchmark) categorizes assets by reliability as investment vehicles and governs the TIQ ceiling. LAQB (Liquidity Asset Quality Benchmark) categorizes assets by reliability as liquidity pair constituents and governs the TLQ ceiling. All three use AAA to CCC classifications with criteria specific to their domain.
