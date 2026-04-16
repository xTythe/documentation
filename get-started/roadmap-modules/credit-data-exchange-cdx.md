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

# Credit Data Exchange (CDX)

Raw on-chain data tells you what happened. CDX provides determinstic, predictive data. It enables individuals to monetize their verified credit data through consent-gated, privacy-preserving exchanges, transforming credit history from an extracted resource into a bankable asset.

CDX flips the credit bureau model. Individuals choose what data they share, with whom, at what anonymity level, and at what price. Buyers access institutional-grade credit intelligence built from verified identity, compliance, financial, and behavioral data.&#x20;

Dataset orders are listed by buyers, filled by eligible individuals, compiled by Tythe, and delivered once the minimum fill threshold is reached. Every transaction is consent-gated, no individual's data is accessed, compiled, or delivered without explicit, order-specific opt-in.

<details>

<summary><strong>1. Buyer Listing</strong></summary>

Any verified institution or individual can list a dataset order on the Credit Data Exchange. Listings are categorized under one of three schema types:

* **Finance:** Risk Pricing and Underwriting
* **Intelligence:** AI and Model Training
* **Forensics:** Credit Event Patterning

***

#### Dataset parameters set at listing

**Schema Type:** The category the dataset falls under. Determines how Tythe formats and delivers the credit reports.

**Eligibility Criteria:** Buyer-defined. Determines which individuals are eligible to opt in.

* _By Wallet Address:_ Only whitelisted wallet addresses may opt in. Enables institution-specific datasets (for example, a vault curator listing a dataset exclusively for the wallet addresses that have interacted with their vaults).
* _By TCT Score:_ Minimum TCT score requirement.
* _By MVV Limit:_ Minimum MVV requirement.
* _By Data Type:_ On-Chain Only, or On-Chain and zkTLS-verified Off-Chain.
* _By Data Depth:_ Minimum credit history on Tythe (1mo+, 3mo+, 6mo+, 1yr+).

**Minimum Fill:** Minimum number of individual reports required before the dataset is delivered.

**Maximum Fill:** Maximum number of individual reports the buyer will accept.

**Anonymity Level**

* No identifiers
* CEP DID only
* CEP DID and specified wallet addresses
* CEP Full (all linked wallets, DID, and zk-KYC verified identity)

**Payout per Report:** The dollar amount the buyer commits per eligible participant report delivered.

**Dataset Escrow:** The buyer deposits the full payout commitment at listing. `Total escrow = Payout per Report * by Maximum` Fill. Funds are released to participants as reports are delivered. Unused escrow is returned to the buyer if the dataset closes below Maximum Fill.

</details>

<details>

<summary><strong>2. Individual Opt-In</strong></summary>

Eligible participants are notified on their Tythe Dashboard when a dataset they qualify for is listed. Eligibility is determined automatically against the buyer's configured criteria.

***

#### Surfaced Information (Before Opt-In)

* Buyer identity (institution name or anonymized buyer ID)
* Schema type
* Anonymity level required
* Data depth being requested
* Exact payout amount

***

#### Opt-In Mechanics

* Participant reviews the listing and chooses to opt in or ignore. No obligation. No penalty for ignoring.
* Once opted in, Tythe automatically compiles the participant's credit report according to the dataset's anonymity level and data type requirements.
* Compiled reports are held until Minimum Fill is reached.
* Once Minimum Fill is reached, all reports are delivered to the buyer simultaneously and payouts are released.

Participant consent is specific and informed. Opting into one dataset does not constitute consent for any other. Each listing requires independent opt-in. A participant can withdraw consent before Minimum Fill is reached and their report is delivered.

</details>

<details>

<summary><strong>3. Report Delivery</strong></summary>

Once Minimum Fill is reached, Tythe compiles and delivers all opted-in participant reports to the buyer simultaneously. Reports are structured according to the Tythe Credit Report standard and formatted for the dataset's schema type.

***

#### Tythe Credit Report Format

**Identity Layer** _(per anonymity level selected)_

* CEP DID
* Primary and secondary wallet addresses
* zk-KYC verification status

**Credit Summary**

* TCT Score and bracket
* MVV limit
* CAVB collateral distribution (% breakdown by tier across the configured lookback period)

**Behavioral Credibility Breakdown** _(Eight behavioral subscores and top contributing events)_

* Historical Performance (35%)
* Current Risk / LaR (20%)
* Credit Utilization (15%)
* New Credit (10%)
* Volatility Quotient (6%)
* Credit Mix (5%)
* Investor Status (5%)
* Action Integrity (4%)

**Capital Capacity Breakdown** _(Four capacity markers and top contributing signals)_

* Total Net Worth (35%)
* Liquidity Provision and Staking (25%)
* Verified Cashflow (25%)
* Average Transaction Value (15%)

**ML Relay Emitter Labels**&#x20;

* All labels received during the lookback period with event typology, percentile rank, TCT delta, and epoch timestamp.

Reports are delivered as standardized, machine-readable files. Buyers receive one report per opted-in participant up to Maximum Fill. No raw underlying data is exposed. No ongoing data access is granted after delivery. Each dataset order is a one-time transaction.

</details>

<details>

<summary><strong>4. Payout Mechanics</strong></summary>

Once reports are delivered, payouts are distributed automatically from escrow. No manual claiming required.

* Each seller receives their Payout per Report directly to their connected wallet
* Tythe deducts a 9% platform cut from each individual payout before distribution
* All payouts release simultaneously at delivery

***

#### Dataset Lifecycle

* **Below Minimum Fill:** Buyer can cancel the order at any time. No data is shared, no charges apply, full escrow is returned to the buyer.
* **At or above Minimum Fill:** The order is locked. The buyer cannot cancel. The buyer can close the order at any time to stop accepting new opt-ins. All reports compiled up to the close point are delivered and charged. No further activity on the dataset after close.
* **At Maximum Fill:** The order auto-closes. Full dataset delivered as final.

***

#### Individual Withdrawal Conditions

* Their report is removed from the dataset
* If withdrawal drops the count below Minimum Fill, delivery pauses until a replacement opt-in restores the count or the buyer cancels the order and receives full escrow back
* The withdrawing participant receives no payout

***

All delivered reports are non-refundable up to the delivered count.

</details>
