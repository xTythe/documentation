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

**The Problem.** Three problems exist across on-chain financial markets today.

1. **Anonymous counterparties.** Every wallet is unknown by default. Protocols cannot distinguish reliable participants from bad actors. Institutions cannot verify users without exposing private data. There is no portable standard for financial identity.
2. **Undifferentiated risk pricing.** Every participant gets the same terms regardless of their track record. High-reliability participants are overcharged due to static rates set for low-reliability participants. Capital efficiency suffers on both sides.
3. **Over-collateralization as the default.** DeFi's answer to trust was to demand everything upfront. To borrow $1, lock up $1.50. Capital trapped in collateral is capital that cannot work. There is no path to credit-based efficiency without a credit standard to build on.

***

**Tythe Protocol.** The neutral infrastructure layer. Open, composable, and buildable by anyone. Tythe Protocol provides the identity, intelligence, integration, and data primitives that on-chain financial markets need to price risk accurately and deploy capital efficiently.

* **Credit Profile.** A self-sovereign identity anchored on the `did:cheqd` network. Unifies wallets, credentials, attestations, and credit history into one portable, regulatory compliant, privacy-preserving profile. Built and owned by individuals. Resolved and verified by markets.
* **Credit Intelligence.** The full picture of an individual's creditworthiness. Character determines the credit score. Capacity determines the credit limit. Together they give any integrated market a complete, enforceable credit signal in real time.
  * **TCT (Tokenized Creditworthiness).** A non-transferable on-chain credit score from 300 to 850. A pure character signal earned through seven behavioral inputs and lost through verified negative events.
  * **MVV (Maximum Vouchsafed Value).** The protocol's assessed credit limit, sized by capital capacity. Expressed as a per-transaction ceiling (tMVV) and a 30-day rolling budget (rMVV).
  * **Relay Emitter.** The protocol's live risk feed. An ML-powered layer that monitors on-chain behavioral patterns, classifies negative credit events, and ranks each participant by severity within their event category. Internally it drives Auto-Slash enforcement. Externally it delivers real-time risk-alpha to institutional subscribers before it moves markets.
* **Credit Adjustment.** The on-chain primitive that puts credit intelligence to work. The Credit Adjustment Layer (CAL) reads a individual's credit profile (score and limit) at transaction time and automatically applies credit-differentiated adjustments to any integrated market. Better terms for reliable participants. Tighter terms for risky ones. No manual underwriting. No static rate tables.
* **Credit Data.** The Credit Data Exchange (CDX) enables consent-gated sale of verified credit data from individuals to institutional buyers. Buyers list dataset orders. Participants opt in on their own terms. Tythe compiles and delivers at minimum fill. Every transaction is order-specific and consent-gated. No data is accessed, compiled, or delivered without explicit individual opt-in.

***

**Tythe Prime.** The capital efficiency market built natively on the Tythe Protocol stack. Accessible to Prime (670+ TCT) and Superprime (780+ TCT) participants only. Tythe Prime is where the protocol's credit intelligence translates directly into better capital terms. Borrowers access positions they could not otherwise reach. LPs deploy capital into a credit-differentiated market where every counterparty is verified and scored. Curators build and manage vaults with full parameter control.

* **Prime Efficient:** A risk-adjusted lending market where every borrower's terms are calibrated to their exact TCT score. Curators set standard parameters reflecting their maximum risk exposure. CAL adjusts rates and LTV ratios from those standards based on each borrower's credit profile. Better TCT and MVV health means better terms. Borrowers pay a membership fee for vault access. The market can range from being efficiently overcollateralized to selective undercollateralized depending on vault-specific curator configuration and borrower risk profile.
* **Collateral Maximization:** A borrowing power amplifier for Superprime borrowers (780+ TCT). Borrowers post collateral and receive a vault contribution top-off that increases their borrowing power beyond what their collateral alone supports. Positions open on a target lending market or inside a Prime Efficient vault. The vault contribution is sized by the borrower's collateral and capped at their tMVV. Additionally, the vault contribution is deducted from the borrower's rMVV.&#x20;
* **Default Insurance:** An internal backstop for Prime Efficient and Collateral Maximization vaults that opt in. A matching-based system where Insurance LPs (Sellers) specify the risk profiles they are willing to cover and their minimum premium. Vault LPs (Buyers) specify the coverage they need and the maximum premium they will pay. The protocol matches on overlap. Idle insurance capital earns yield through curator-deployed float strategies. Coverage is optional for KYC-verified vaults. For zk-KYC vaults without coverage, protocol guardrails apply automatically.

Collateral Maximization increases the quantity of capital a borrower can access. Prime Efficient optimizes the terms they get on it. Default Insurance becomes the guardrail that protects vault-active LPs. The three products are designed to stack.

***

**Tythe DAO.** The decentralized governance and arbitration layer of the Tythe Protocol. No single entity, including Tythe, can unilaterally control scoring parameters, dispute outcomes, or protocol direction. Two arms, distinct functions, deliberate separation between them.

* **Justice Arm.** Handles disputed slashes and contested scoring events. AI clerks prepare evidence briefs from on-chain data. Human juries drawn from the same TCT band as the disputant hear and resolve each case. To raise a dispute, participants stake a protocol-defined amount of TCT as a good faith deposit. Burned if the slash is upheld. Returned in full if overturned. No legal representation required. On-chain history is the only evidence that matters.
* **Governance Arm.** Manages scoring parameters, formula upgrades, treasury allocation, and protocol direction via the TYT token. Activates once TYT is live and the protocol has established a verifiable data foundation worth governing. Two voting tracks operate independently: Track 1 for formula governance requires both a minimum TCT threshold and TYT holdings. Track 2 for all other protocol decisions uses pure TYT weighting. Formula weights are visible to institutional DAO members only, preventing gaming without sacrificing accountability.
