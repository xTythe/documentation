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

**Tythe Prime.** The capital efficiency space built natively on the Tythe Protocol stack. Accessible to Prime (670+ TCT) and Superprime (780+ TCT) participants only. Tythe Prime is where the protocol's credit intelligence translates directly into better capital terms. Borrowers access positions they could not otherwise reach. LPs deploy capital into a credit-differentiated market where every counterparty is verified and scored. Curators build and manage vaults with full parameter control.

* **Prime Efficient.** A native lending market offering personalized rates and terms calibrated to each borrower's exact TCT score and MVV. Better rates and better collateral-to-loan ratios than anonymous DeFi markets. Borrowers pay a membership fee for access to the superior terms tier that matches their usage profile. No two borrowers get identical terms. Character and capacity determine everything.
* **Collateral Maximization.** A credit line product for Superprime borrowers. Participants post collateral and receive a vault contribution top-off that increases their borrowing power beyond what their collateral alone supports. Positions open on a target lending market or inside a Prime Efficient vault. The vault contribution is sized by the borrower's collateral and capped at their tMVV. LPs provide the capital and earn yield for doing so.
* **Default Insurance.** An institutional product available on the Institutional Dashboard. Lending markets buy protection against borrower defaults in their pools. Vault LPs are the protection sellers. Premium pricing is driven by Tythe's TCT scoring data, making it the first on-chain default insurance product with a genuine credit intelligence foundation. Borrowers are never notified and are not a party to the arrangement.

***

**Tythe DAO.** The decentralized governance and arbitration layer of the Tythe Protocol. No single entity, including Tythe, can unilaterally control scoring parameters, dispute outcomes, or protocol direction. Two arms, distinct functions, deliberate separation between them.

* **Justice Arm.** Handles disputed slashes and contested scoring events. AI clerks prepare evidence briefs from on-chain data. Human juries drawn from the same TCT band as the disputant hear and resolve each case. To raise a dispute, participants stake a protocol-defined amount of TCT as a good faith deposit. Burned if the slash is upheld. Returned in full if overturned. No legal representation required. On-chain history is the only evidence that matters.
* **Governance Arm.** Manages scoring parameters, formula upgrades, treasury allocation, and protocol direction via the TYT token. Activates once TYT is live and the protocol has established a verifiable data foundation worth governing. Two voting tracks operate independently: Track 1 for formula governance requires both a minimum TCT threshold and TYT holdings. Track 2 for all other protocol decisions uses pure TYT weighting. Formula weights are visible to institutional DAO members only, preventing gaming without sacrificing accountability.
