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

# The Tythe Protocol

Tythe is the neutral, decentralized protocol for credit. It turns on-chain behavior into verifiable creditworthiness that any onchain market can use to price risk and deploy capital.

***

#### The Problem

On-chain finance has three structural problems.

**Anonymous counterparties.** Every wallet is unknown by default. Protocols cannot tell a reliable participant from a bad actor. There is no portable standard for financial identity.

**Undifferentiated pricing.** Every participant gets the same terms regardless of track record. Reliable participants subsidize the unreliable. Capital efficiency suffers on both sides.

**Overcollateralization as the default.** To borrow a dollar, lock up more than a dollar. Capital that sits in collateral cannot work elsewhere. There is no path past this without a credit standard to build on.

***

#### The Stack

**Tythe Credit Intelligence.** The data layer that produces the scores, reports, and indices describing credit on-chain.

**Tythe Prime Markets.** Permissionless prime brokerage infrastructure that uses existing onchain markets as the liquidity and liquidation layer, and provides the credit and efficiency layer on top.

**Tythe DAO Governance.** The governance layer launching alongside the TYT token post testnet.

***

#### Tythe Credit Intelligence

**1. Credit Scores**

A numeric measure of financial credibility. Integer between 300 and 850, with reserved low-end values for participants without sufficient data (score = 1) or with verified protocol exploits in their history (score = 0).

* **Borrower Score.** Credibility for collateralized borrowing. Computed from a participant's history across integrated lending venues such as Aave, Morpho, Spark, and Compound.\
  Euler, Sky, and Fluid venue support post-launch.
* **Trader Score.** Counterparty safety for leveraged perpetuals trading. Computed from a participant's history across integrated perp venues such as Hyperliquid and EdgeX.\
  Aster, ApeX, and dYdX venue support post-launch.

Both scores can be issued against a single wallet or against an aggregated profile linking multiple wallets to one credit identity.

**2. Credit Reports**

The full account of behavior behind a score. The positions, the events, the trajectory.

* **Borrower Report.** The borrowing history backing a Borrower Score. Positions, repayments, liquidations, exposure over time.
* **Trader Report.** The trading history backing a Trader Score. Positions, liquidations, leverage, performance over time.

Both reports can be issued against a single wallet or against an aggregated profile linking multiple wallets to one credit identity. Reports are produced for distinct audiences: Risk and Underwriting (Finance), AI and Machine Training (Intelligence), Modeling and Analysis (Research), with the report field set tuned to each.

**3. Credit Indices**

Market-level and asset-level signals derived from the same data layer as the scores.

* **Market Risk Index.** Measures the risk relationship between a market and its counterparty users. Anyone can deploy an index for any market by specifying its risk structure once and maintaining its participant list. The contract reads each participant's scores and computes aggregate risk from both directions; the market's risk to its counterparties, and the counterparties' risk to the market.

Market Risk Indices can be deployed permissionlessly against existing markets (a live Aave pool, a Morpho market, a Hyperliquid pair, an insurance/coverage app \[such as the Aave app], a card program \[for example, the Coinbase One credit card]) or against test markets (hypothetical configurations used to evaluate risk before deployment).

***

### Tythe Prime Markets

Tythe Prime is permissionless prime brokerage infrastructure that uses existing onchain markets as venues. Tythe Prime provides the credit and efficiency layer for these markets to offer better deals to their customers and users without changing their platform's risk appetite. Brokers create and operate brokerage markets that combine depositor collateral with liquidity provider capital to open credit-amplified positions on the target venue. Depositors access positions beyond what their collateral alone supports; liquidity providers earn fees from the markets they fund; brokers run credit policy and set native terms. Two market types: Public Broker Markets are permissionless, single-venue, and parameter-locked at deployment; Private Broker Markets are invite-only and support multi-venue portfolio construction. Access requires a Borrower Score of 670 (or higher) to access Brokerage Money Markets or a Trader Score of 670 (or higher) to access Brokerage Trading Markets.

***

### Tythe DAO Governance

The decentralized autonomous organization of the Tythe protocol. No single entity, including the Tythe team, controls scoring parameters, dispute resolution, or protocol direction unilaterally. The DAO launches alongside the TYT token before mainnet launch, with initial scope covering scoring parameter adjustment, treasury, protocol direction, and distribution of TYT rewards to ecosystem participants (liquidity providers, brokers, and high-credibility borrowers and traders). Disputes over scoring events are reviewed by a machine learning model trained on the same behavioral data that feeds the scores.
