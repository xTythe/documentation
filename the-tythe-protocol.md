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

# The Tythe Protocol

Tythe is the neutral, decentralized protocol for credit. It provides the infrastructure to transform on-chain behavioral data into verifiable creditworthiness across on-chain finance.

***

**What Tythe Builds**

Three problems exist across on-chain financial markets. Tythe solves all three with a single, composable protocol stack.

1. **Anonymous counterparties.** Every wallet is unknown by default. Protocols cannot distinguish reliable participants from bad actors. Institutions cannot verify users without exposing private data. There is no portable standard for financial identity.
2. **Undifferentiated risk pricing.** Every participant gets the same terms regardless of their track record. High-reliability participants are overcharged. Low-reliability participants are underpriced. Capital efficiency suffers on both sides.
3. **Over-collateralization as the default.** DeFi's answer to trust was to demand everything upfront. To borrow $1, lock up $1.50. Capital trapped in collateral is capital that cannot work. There is no path to credit-based efficiency without a credit standard to build on.

***

**The Protocol Stack**

* **Identity (CEP):** The Credit Enhancement Profile is a permanent, user-owned financial identity anchored on the `did:cheqd` network. It unifies wallets, credentials, attestations, and credit history into one sovereign, privacy-preserving profile. Every participant in the protocol builds from a CEP.
* **On-Chain Intelligence (TCT):** The Tokenized Creditworthiness score (300 to 850) is a non-transferable ERC-20 token representing verified financial reliability. TCT is a pure character score earned through seven behavioral inputs and lost through verified negative events. Embedded in its metadata are two credit limits that extend the protocol's intelligence surface beyond character.
  * **tMVV (per-transaction credit limit):** The maximum value-based enhancement the protocol will apply on any single transaction. A hard ceiling per transaction sized to the participant's verified capital capacity.
  * **rMVV (30-day rolling credit limit):** The participant's total enhancement budget across all transactions in a 30-day window. rMVV = tMVV × 10. Depletes in real time as enhancements are applied across integrated markets. Resets automatically every 30 days.
* **Off-Chain Intelligence (Relay Emitter):** An ML-powered intelligence layer built on gradient boosting models (XGBoost and LightGBM). Monitors on-chain behavioral patterns, classifies negative credit events into labeled categories, and ranks each participant within their label's spectrum by severity. Institutional subscribers receive ranked nEvent labels via tiered subscription feeds with configurable data pool size, user count, and cadence.
* **Integration (CEW):** The Credit Enhancement Wrapper intercepts financial transactions at execution time and applies TCT-based credit logic automatically. Rate discounts, collateral reductions, and fee adjustments for high-reliability participants. Tighter terms and enforcement for low-reliability ones. Hard denial for blacklisted wallets. No manual underwriting. No static rate tables.
* **Governance & Justice (Tythe DAO):** The Justice Arm resolves disputed slashes through decentralized arbitration. AI clerks prepare evidence briefs. Human juries drawn from the disputant's TCT band deliver verdicts. The Governance Arm manages scoring parameters and formula upgrades via the TYT token. zkTLS extends the scoring surface to verified off-chain financial data without exposing raw records.
* **Liquidity** **(CEV):** Credit Enhancement Vaults are the only module enabling undercollateralized lending on Tythe. LPs provide collateral backing to support TCT-verified borrowers on existing integrated lending markets. CEV owns every position it opens. The borrower interacts with CEV only, never with the lending market directly. Risk is distributed across LPs who opt in explicitly for yield and risk premiums.
* **Data** **(CDX):** The Credit Data Exchange enables consent-gated sale of verified credit data from individuals to institutional buyers. Participants set their terms. Buyers list dataset orders. Tythe compiles and delivers at minimum fill.&#x20;

> Agentic Credit extends the same stack to verified AI agents, letting them leverage execution history for protocol-backed credit lines.
