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
---

# The Tythe Protocol

Tythe is a decentralized orchestration layer designed to establish the first global standard for assetized credibility. It serves as the foundational infrastructure for a risk-intelligent, borderless economy, empowering humans and AI agents with a credibility profile that proves their reliability (the ability to carry risk) without compromising their privacy or relying on centralized intermediaries. For digital institutions, DeFi protocols, DAOs, and cross-sector applications, Tythe provides the critical rails to scale operations by offloading data liability, automating risk enforcement, and mitigating wallet disposability risks with verifiable, real-time intelligence.

<details>

<summary><strong>The Definition:</strong> <strong>What is Credibility?</strong></summary>

Inside the Tythe ecosystem, credibility is treated as a multi-dimensional asset. While traditional systems focus narrowly on creditworthiness, Tythe recognizes that the complete picture of any actor's reliability is a composite of diverse, verifiable signals across various landscapes.

To achieve comprehensive inclusivity, greater accuracy, and higher granularity for increased predictive power, Tythe is built to aggregate intelligence across five primary metrics:

<figure><img src=".gitbook/assets/Image 1-25-26 at 10.36 PM.png" alt=""><figcaption></figcaption></figure>

* **Compliance Reliability:** Verifies adherence to global and local regulatory frameworks. This covers Proof of Humanity/KYC/AML status, jurisdictional eligibility, and sanction-list screening. It ensures that actors meet rigorous compliance standards for institutional interaction without ever exposing PII to the network.
* **Financial Reliability:** Measures total solvency and capital efficiency. This includes verified income and employment, historical repayment reliability, and granular DeFi activity (lending, borrowing, staking, LP positioning, and trading). It further accounts for tokenized asset experience—including Real-World Asset (RWA) exposure, portfolio management, and liquidity depth—incorporating and superseding traditional Creditworthiness.
* **Governance Reliability:** Evaluates the quality of participation within decentralized structures. This tracks on-chain voting history, proposal frequency, delegation reliability, and alignment with protocol-specific standards, distinguishing active, value-aligned contributors from passive or extractive actors.
* **Security Reliability**: Assesses the technical and operational integrity of an actor. For developers, this includes smart contract authorship and audit history; for operators, it monitors validator uptime, slashing history, and secure key management behavior. This metric ensures that the "Trust Fabric" is technically sound.
* **Sustainability Reliability:** Tracks impact-weighted trust and alignment with ESG (Environmental, Social, and Governance) initiatives. This includes participation in carbon markets, sustainability-linked finance, and social impact programs, rewarding actors whose behavioral data reflects long-term environmental and social responsibility.

</details>

<details>

<summary><strong>The Problem:</strong> <strong>Why is Credibility needed?</strong></summary>

The transition to a credibility-based model is a response to the systemic failures of the models that preceded it.

* The Failure of Legacy Credit (Gen 1): Traditional off-chain models rely on black-box algorithms and centralized bureaus that store sensitive PII leading to single point failures (like Equifax 2017, where a single breach exposed the data of 147 million people). These systems also suffer from jurisdictional limitations (your score is meaningless the moment you cross your national border) and lagging reports that compromise user sovereignty and impose an "AI ceiling," effectively excluding autonomous agents and millions of "thin-file" humans while trapping global liquidity.
* The Limits of Wallet Analytics (Gen 2): Early on-chain models improved transparency but remain tethered to disposable wallet addresses. Without an orchestrated identity layer, they are highly vulnerable to Sybil manipulation and identity recycling, failing to provide the long-term accountability or multi-sector depth required for institutional enforcement.

</details>

<details>

<summary><strong>The Solution:</strong> <strong>How does Tythe work?</strong></summary>

Tythe solves these systemic failures by introducing a zk-private orchestration layer that bridges the gap between raw data and actionable risk-intelligence. The protocol does not merely "score" a user; it manages the entire lifecycle of credibility through a robust, modular stack.

\ <mark style="color:$primary;">**Live Modules:**</mark> These core components are operational and form the immediate utility of the protocol during the launch phase:

* **Self-Sovereign DIDs:** Every participant—human or agent—anchors their decentralized identity on the `did:cheqd` network. This provides a persistent, globally unique identifier that remains decoupled from biological data or fragmented wallet addresses.
* **Proof of Liability:** Tythe solves the AI reliability gap by establishing a legally-binding cryptographic link between an autonomous agent and its human or organizational Registrant via a Ricardian Contract. This ensures every automated action is programmatically auditable and anchored to an accountable entity.\
  &#xNAN;_(Note: This feature is currently in development and will launch post-Beta)._
* **Personal Encrypted Ledgers:** During the current phase, the Trovebook acts as an encrypted ledger for all verified activity. This will transition to a fully self-custodial ledger with local private key management during the Mainnet migration.
* **Verifiable Credentials (VCs):** Important identity compliance attestations—Proof of Humanity/KYC/AML checks—are issued as W3C-compliant VCs. These are portable, tamper-proof, and can be presented to any verifier.
* **Zero-Knowledge Proofs:** Users prove eligibility (e.g., "I am a qualified investor", "I am a reliable borrower", "I have high voting integrity") without revealing the underlying data, ensuring 0% PII exposure.
* **Standardized Scores & Health Factors:** The DISC Engine transforms raw behavior into a 7–100 score and granular health factors (0.000–1.000), providing a high-fidelity snapshot of an actor’s multi-sector reliability and a universal language for reliability that institutions can underwrite.
* **Privacy-Configurable Reports:** Similar to traditional credit reports, DISC Reports are off-chain, portable documents that allow users to share their verified standing with external institutions on their own terms.
* **Policy-as-Code (VPs & APs):** Organizations define exactly how credibility is earned on for users on their platform by writing Validation Policies (VPs) using a standard set of automated behavioral-trigger rules. Access Policies (APs) are implemented to gate products and services behind credibility thresholds and compliance requirements. This removes human bias and black-box interference from the trust process.
* **Decentralized Validation:** The Tri-Validator Model ensures that no single entity controls the standard. Verification is distributed across Organizational (for behavioral validation), Peer (for social reputation), and Jury validators (for network-wide enforcement at the root ID level) to eliminate bias, identity recycling, and central points of failure.

\ <mark style="color:$info;">**Locked Modules:**</mark> The following modules represent the strategic evolution of the protocol and are currently in the final stages of research and development:

* Proof of Liability: Utilizing Ricardian Contracts, this module will bind AI Agents to their human or organizational registrants, creating a legal and economic anchor for autonomous operations.
* Credibility-Weighted Governance: A specialized governance framework where voting power is a function of both token stake and the participant’s DISC score, ensuring that those with the highest verified "skin in the game" lead the protocol.
* The tCDX Stack: The introduction of tCDL (Data Licensing), tCDS (Credibility Swaps), and tCDSI (Indexes), turning credibility into a liquid financial asset class.
* Dual Token Model: The formal launch of TCT (the internal unit of credibility) and TYT (the utility and governance token).

</details>
