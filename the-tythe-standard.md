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
  actions:
    visible: true
---

# The Tythe Standard

The **Tythe** **Credit Intelligence** standard defines how financial and behavioral data is transformed into the verifiable credit signals that underlie everything in the Tythe Credit Intelligence stack: Credit Scores, Credit Reports, and Credit Indices.

Tythe Credit Intelligence 26 is the launch model. Both Credit Scores are computed off-chain by the scoring engine, signed via EIP-712 attestation, and anchored on-chain by the participant at Refresh, or by the backend when a Negative Event is detected.

***

#### Compliance Gate

Compliance is a binary prerequisite. The scoring engine remains dormant until compliance conditions are met. No score is computed or attested without a verified Compliance Gate.

**Mandatory at registration:**

* **Proof of Personhood via World ID.** Biometric-anchored Sybil resistance. One human, one credit identity. Mandatory at profile creation.
* **Primary Wallet Address.** A verified wallet bound to the `did:cheqd` identifier as DID-Linked Resource (DLR). V1 launches on Base with additional support for top-EVM wallets such as MetaMask, Rabby, Trust Wallet, and more.

**Optional post-registration:**

* **Additional wallets.** Multi-wallet connectivity via a two-signature `LinkWallet` flow on the Attestation Registry. Linking signals that a participant is aggregating their on-chain history into one credit identity. All linked wallets contribute to the aggregated profile's scores.

Once mandatory conditions are met, a `did:cheqd` identifier is the participant's permanent credit identifier within the Tythe protocol.

> **Protocol Note.** If a participant's profile is blacklisted via verified Exploit, both scores are forced to 0 and the profile is terminally revoked. Blacklist reversal requires an explicit unblacklist attestation, available only through the dispute review pipeline.

***

#### Credit Scores

Two scores, both produced by the same scoring engine, both anchored on the same on-chain contract under a combined dual-score attestation.

<details>

<summary><strong>Tythe Borrower Score</strong></summary>

Measures credibility for collateralized borrowing across integrated lending venues. Integer in `{0, 1} ∪ [300, 850]`.

Six subscores, weighted to produce a probability of borrower failure that maps to the final score.

| Subscore               | Weight | What it measures                                                                                                                                       |
| ---------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Historical Performance | 35%    | Successful loan fulfillment across a 24-month window. Defaults carry heavy decay. Longest memory in the formula.                                       |
| Current Risk           | 23%    | Aggregate Liabilities at Risk across all linked wallets against real-time collateral. Captures live solvency exposure via stochastic price simulation. |
| Credit Utilization     | 15%    | Delta between current loan-to-value and the maximum permitted loan-to-value across active positions. Edge-behavior is penalized.                       |
| New Credit             | 10%    | Frequency of new debt origination. Detects financial distress or predatory borrowing patterns.                                                         |
| Volatility Quotient    | 9%     | Exposure to low-liquidity or high-volatility collateral. Calibrated by the Asset Volatility Benchmark.                                                 |
| Credit Mix             | 8%     | Sophistication of credit history, including vault complexity, blue-chip depth, protocol and position diversity.                                        |

</details>

<details>

<summary><strong>Tythe Trader Score</strong></summary>

Measures counterparty safety for leveraged perpetuals trading across integrated perp venues. Integer in `{0, 1} ∪ [300, 850]`.

Six subscores, weighted to produce a probability of counterparty failure that maps to the final score.

| Subscore              | Weight | What it measures                                                                                                          |
| --------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------- |
| Historical Harm       | 35%    | Ratio of liquidation volume to terminating-event volume over a 24-month window, combined with per-event severity.         |
| Current Risk          | 23%    | Probability that any currently open position liquidates within a 7-day forward horizon under stochastic price simulation. |
| Leverage Utilization  | 15%    | Notional-time-weighted average effective leverage across currently open positions.                                        |
| Volatility Resilience | 10%    | Realized liquidation rate on positions held during high-volatility regimes versus low-volatility regimes.                 |
| Close Calls           | 9%     | Frequency of near-miss events where margin ratio approached the liquidation threshold without crossing it.                |
| Trader Quality        | 8%     | Composite of activity, experience, and luck-resistant profitability (profit factor over a 365-day window).                |

</details>



1.  **Score States**<br>

    | Value   | State   | Meaning                                                                                   |
    | ------- | ------- | ----------------------------------------------------------------------------------------- |
    | 300–850 | Scored  | Probability-derived credibility score.                                                    |
    | 1       | No Data | Insufficient or stale activity to score the participant. Reversible by resuming activity. |
    | 0       | Slashed | Verified Exploit; profile terminally revoked.                                             |



2.  **Risk Brackets:** Brackets are descriptive. TThey map score ranges to qualitative tiers so participants and counterparties can contextualize what a score means. Markets and integrations consume the underlying integer score directly.\
    \
    &#xNAN;_&#x4E;ote:_ _Bracket boundaries are identical for both the Tythe Borrower Score and the Tythe Trader Score. Both scores use the same probability-to-integer transformation, so the integer-to-bracket mapping is mathematically shared and consistent._<br>

    <table><thead><tr><th width="350">Range</th><th>Bracket</th></tr></thead><tbody><tr><td>800–850</td><td>Excellent</td></tr><tr><td>740–799</td><td>Very Good</td></tr><tr><td>670–739</td><td>Good</td></tr><tr><td>580–669</td><td>Fair</td></tr><tr><td>300–579</td><td>Poor</td></tr><tr><td>1</td><td>No Data</td></tr><tr><td>0</td><td>Slashed</td></tr></tbody></table>


3. **Scores Updates:** Three update mechanisms operate against each score.

* **Participant Refresh (On-Chain).** \
  Voluntary update. The participant pays gas to anchor a new score on-chain. Triggered typically before opening a new position where score-driven terms matter.
* **Negative Event (On-Chain).** \
  Automatic update fired by the backend when a qualifying on-chain event is detected (liquidation, default, exploit). The backend pays gas. The participant takes no action.
* **Backend Recompute (Off-Chain).** \
  The backend runs the full scoring pipeline every 15 minutes against every scored participant and stores the result as the participant's current off-chain score. The off-chain score does not update on-chain state. It informs the participant via notification when a Refresh would meaningfully change their on-chain score.\
  \
  A participant's on-chain score is the externally verifiable value at the time of their last Refresh or Negative Event. The off-chain score is the participant's current state at any given moment.\
  \
  Subscore weights are fixed at launch. Adjustments require a successful Tythe DAO governance proposal with mandatory timelock.\
  \
  Both scores can be issued against an arbitrary wallet or against an aggregated profile linking multiple wallets to one credit identity.

***

#### Asset Volatility Benchmark

The Asset Volatility Benchmark is a 7-tier classification of on-chain assets, governing how volatility factors into scoring math and risk-adjacent calculations. Tiers run from AAA to CCC.

| Class | Standard                                                               |
| ----- | ---------------------------------------------------------------------- |
| AAA   | Major stablecoins, tokenized gold, T-bills, money market funds         |
| AA    | Bitcoin, Ether, liquid staking tokens, short-term tokenized treasuries |
| A     | Top 3–40 by market cap, tokenized equities                             |
| BBB   | Top 41–100 by market cap, tokenized private credit                     |
| BB    | Top 101–150 by market cap, mid-cap memes, tokenized real estate        |
| B     | Top 151–300 by market cap, tokenized physical assets                   |
| CCC   | All other assets (catchall)                                            |

The benchmark is library-resident and governance-versioned — updates ship as library releases approved by Tythe DAO. CCC-classified assets reduce the Volatility Quotient subscore in Tythe Borrower Score and contribute to Volatility-weighted Historical Harm in Tythe Trader Score.

The Asset Volatility Benchmark is also the foundation for the Asset Volatility Index, an externally-exposed Credit Index product that exposes asset-level volatility signals to integrated markets and risk consumers.

***

#### Negative Events

Verifiable on-chain events that trigger immediate Recompute. Negative Events skip the participant's voluntary Refresh; the backend signs and submits an attestation as soon as the event is detected on the venue feed.

Severity is captured naturally through the scoring formula. A small partial liquidation moves the score modestly. A full liquidation with significant bad debt moves it substantially. An Exploit forces the score to 0.



1. **Tythe Borrower Score Negative Events**

| Event       | Trigger                                                                                                                      | Effect                                                                        |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Liquidation | Collateral failure on an integrated lending venue                                                                            | Negative Event                                                                |
| Default     | Failure to fulfill debt within grace period (fixed-term loans past due, or persistent at-risk positions on open-term venues) | Negative Event                                                                |
| Exploit     | Verified involvement in a smart-contract attack                                                                              | Score forced to 0, profile blacklisted on the Attestation Registry. Terminal. |

2. **Tythe Trader Score Negative Events**

| Event                | Trigger                                                | Effect                                                                        |
| -------------------- | ------------------------------------------------------ | ----------------------------------------------------------------------------- |
| Position Liquidation | Full or partial liquidation by the perp venue's engine | Negative Event                                                                |
| Exploit              | Verified involvement in a smart-contract attack        | Score forced to 0, profile blacklisted on the Attestation Registry. Terminal. |

Exploits are a Negative Event subtype across both scores. They bypass the normal scoring pipeline, force the score to 0, and blacklist the profile via a separate cryptographic role. The cost of a false-positive blacklist is high (exploit classification requires manual verification before attestation).

Disputed Negative Events are reviewed by a machine learning model (gradient-boosted, LightGBM/XGBoost architecture) trained on the same behavioral data that feeds the scores. The same model architecture serves both Tythe Borrower Score and Tythe Trader Score disputes. Overturned Exploit classifications produce an unblacklist attestation that restores the profile to active status.

***

#### Open Source Commitment

Tythe operates a three-tier transparency model. The goal is full credibility on the system's mechanics while protecting the protocol from formula-gaming.

**1. Smart contract code.** Fully open source. Auditable by anyone, always. Non-negotiable.

**2. Methodology structure.** Publicly documented. Subscore names and weight signatures, the Compliance Gate conditions, the Asset Volatility Benchmark tier structure, the Negative Event typology, the recompute trigger structure. Anyone reading these docs can understand the shape of what drives a score and why.

**3. Math and formulas.** Proprietary. Specific anchor curve values, sigmoid centers, Monte Carlo convergence parameters, score transform constants, and Credit Adjustment interpolation math are sealed under DAO license. Visible only to institutional DAO members. Modifications require successful governance proposal with mandatory timelock.

This balance prevents bad actors from reverse-engineering optimal exploitation patterns against the scoring math while preserving full accountability on the system's mechanics. Everything that lets a participant understand their score is public; the deep parametric values that would let an adversary precisely game the formula stay sealed.

***

#### The Evolving Standard

Tythe Credit Intelligence V1 is the launch model. Future versions activate only via successful Tythe DAO governance proposal with mandatory timelock. No scoring change takes effect without community oversight.

The most immediate forward direction is **zkTLS-verified off-chain financials.** Bank balance proofs, payroll attestations, tax filings, and other off-chain financial signals integrate into the scoring math via zero-knowledge proofs. No raw financial data leaves the participant's custody, only the verified claim is consumed by the scoring engine. This extension is well-defined in shape and sequenced after V1.

Subsequent versions may integrate additional telemetry as DAO governance approves them.

***

#### FAQs

**1. Why should we trust Tythe's scores?**

Determinism. Every score update is backed by a verifiable on-chain event or a zero-knowledge proof. The smart contract code is fully open source. The methodology structure is publicly documented. The scoring engine produces an attested score signed via EIP-712 and anchored on-chain. The signature is verifiable, the inputs are traceable, the math is repeatable. A score is not a black-box opinion. It is a computation against a documented standard, with cryptographic provenance at every step.&#x20;

**2. Does Tythe have authority to freeze user funds?**

No. Tythe is a neutral credit-intelligence layer, not a custodian. The protocol can attest score updates based on verifiable events. Integrated markets make their own independent decisions about whether to adjust or restrict participant positions based on those signals.

**3. How does Tythe prevent Sybil attacks?**

Credit is bound to a single profile; a `did:cheqd` identifier verified by Proof of Personhood via World ID. One human, one credit identity. A participant may link multiple wallets to their profile, but all wallets map to the same root identity. Credibility cannot be artificially multiplied across fake accounts, nor can it be recycled to another one.

**4. What happens if a participant is wrongly slashed?**

Disputed Negative Events are reviewed by a machine learning model (a gradient-boosted classifier (LightGBM/XGBoost architecture) trained on the same behavioral data that feeds the scores). The model adjudicates whether the original classification stands. Overturned classifications result in score restoration. In the case of overturned Exploit classifications, an unblacklist attestation returns the profile to active status.

**5. What is the Asset Volatility Benchmark?**

A 7-tier classification (AAA through CCC) that categorizes on-chain assets by volatility profile and liquidity depth. The benchmark feeds the Volatility Quotient subscore in Tythe Borrower Score and the volatility weighting in Tythe Trader Score's Historical Harm.&#x20;
