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

Tythe is a decentralized orchestration layer designed to establish the first global standard for assetized credibility. It serves as the foundational infrastructure for a risk-intelligent, borderless economy, empowering humans and AI agents with a purpose-built credibility profile that proves their reliability—their ability to carry risk—without limiting the effectiveness of their profile to a single jurisdiction, compromising their privacy, or relying on centralized intermediaries. For digital institutions, DeFi protocols, DAOs, and cross-sector applications, Tythe provides the critical rails to scale operations by offloading risk-data liability, automating risk enforcement, and mitigating wallet disposability risks with verifiable, real-time intelligence.

<details>

<summary><strong>The Definition: What is Credibility?</strong></summary>

In the Tythe ecosystem, "Credibility" is the asset capable of representing an actor's total multi-dimensional reliability. It serves as the aggregated result of verified behavioral signals—spanning across: (_1) Compliance Reliability_, _(2) Financial Reliability_, _(3) Governance Reliability_, _(4) Security Reliability_, and _(5) Sustainability Reliability_ metrics—of which traditional "Creditworthiness" is a sub-component of _Financial Reliability_.

<figure><img src=".gitbook/assets/Image 1-25-26 at 10.36 PM.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
#### Multi-Dimensional Credibility: The Architecture of Purpose-Driven Profiles

The multi-dimensional nature of the DISC Score is not a "one-size-fits-all" umbrella model. Tythe does not mandate high-volume participation across all five metrics to achieve a valid credibility standing. Instead, this architecture is designed for purpose-driven profile building.

We recognize that different humans and AI agents have distinct operational fields; a secure smart contract developer may prioritize Security Reliability, while a DAO delegate may anchor their reputation in Governance Reliability. Credibility is never restricted by rigid metric prioritization, but is instead determined by the verified impact an entity has demonstrated within its specific field of operations.
{% endhint %}

</details>

<details>

<summary><strong>The Evolution:</strong> <strong>How is Credibility better?</strong></summary>

Credibility is the better form of risk-intelligence because it is designed to achieve comprehensive inclusivity, greater accuracy, and higher granularity for increased predictive power and a wider range of use cases using aggregated intelligence across five primary metrics:

* **Compliance Reliability:** Verifies adherence to regulatory frameworks. This covers Proof of Humanity/KYC/AML status, jurisdictional eligibility, and sanction-list screening. It ensures that actors meet rigorous compliance standards for institutional interaction without ever exposing sensitive PII to the network.
* **Financial Reliability:** Measures total solvency and capital efficiency. This includes verified income and employment, historical repayment reliability, and granular DeFi activity (lending, borrowing, staking, LP positioning, and trading). It further accounts for tokenized asset experience—including Real-World Asset (RWA) exposure, portfolio management, liquidity depth, and cashflow—incorporating and superseding traditional creditworthiness.
* **Governance Reliability:** Evaluates the quality of participation within decentralized structures. This tracks on-chain voting history, proposal frequency, delegation reliability, and alignment with protocol-specific standards, distinguishing active, value-aligned contributors from passive or extractive actors.
* **Security Reliability**: Assesses the technical and operational integrity of an actor. For developers, this includes smart contract authorship and audit history; for operators, it monitors validator uptime, slashing history, and secure key management behavior. This metric ensures of technical capabilty and soundness.
* **Sustainability Reliability:** Tracks alignment with ESG (Environmental, Social, and Governance) initiatives. This includes participation in carbon and renewable energy markets, sustainability-linked finance, and social impact programs, rewarding actors whose behavioral data reflects long-term environmental and social responsibility.

</details>

<details>

<summary><strong>The Problem:</strong> <strong>Why is Tythe needed?</strong></summary>

The development of the Tythe standard is a response to the systemic failures and limitations of the models that preceded it.

* Traditional off-chain models: Rely on black-box algorithms and centralized bureaus that store sensitive PII leading to single point failures (like Equifax 2017, where a single breach exposed the data of 147 million people). These systems also suffer from jurisdictional limitations (provided scores are meaningless the moment the scored entity crosses their national border) and lagging reports (these are days or sometimes even weeks out-of-sync with reality) that compromise user sovereignty and impose an "AI ceiling," effectively excluding autonomous agents and millions of "thin-file" humans while trapping global liquidity.
* Current on-chain models: Improve transparency but remain tethered to histories of disposable wallet addresses. Without an orchestrated identity layer, they are highly vulnerable to Sybil manipulation and identity recycling, failing to provide the long-term accountability or multi-sector depth required for institutional enforcement.

</details>

<details>

<summary><strong>The Solution:</strong> <strong>How does Tythe work?</strong></summary>

Tythe solves these systemic failures by introducing a zk-private orchestration layer that bridges the gap between raw data and actionable risk-intelligence. The protocol does not merely "score" a user; it manages the entire lifecycle of credibility through a robust, modular stack.

\ <mark style="color:$primary;">**Live Modules:**</mark> These core components are operational and form the immediate utility of the protocol during the launch phase:

* **Self-Sovereign DIDs:** Every participant—human or agent—anchors their decentralized identity on the `did:cheqd` network. This provides a persistent, globally unique identifier that remains decoupled from biological data or fragmented wallet addresses.
* **Verifiable Credentials (VCs):** Important identity compliance attestations—Proof of Humanity/KYC/AML checks—are issued as W3C-compliant VCs. These are portable, tamper-proof, and can be presented to any verifier.
* **Verifiable Receipts (VRs):** The atomic units of memory inside Tythe. VRs are cryptographically signed proofs of specific events—such as a successful loan repayment or a governance vote—that serve as the raw evidencial inputs for provided risk-intelligence outputs.
* **Private Memory Ledgers:** These ledgers act as credibility footprint repositories that store Verifiable Receipts. During the current phase, these ledgers operate with cloud-based encryption and manageable decryption keys, transitioning to a fully self-custodial model with local private key management during the Mainnet migration.
* **Zero-Knowledge Proofs:** Users prove eligibility (e.g., "I am a qualified investor", "I am a reliable borrower", "I have high voting integrity") without revealing the underlying data, ensuring 0% PII exposure.
* **Standardized Values:** The computation engine transforms raw behavior into a 7–100 credibility score and 0.000–1.000 metric reliability factors for granular, multi-dimensional risk-intelligence. Conversely, negative behavior is categorized using violation codes (1–6), providing a standardized numerical language for reliability and misconduct that institutions can underwrite with confidence.
* **Configurable Reports:** Similar to traditional credit reports, reports generated by Tythe are off-chain, portable documents that allow users to share their verified standing with external institutions. .
* **Policy-as-Code (VPs & APs):** Organizations define exactly how credibility is earned or lost for users on their platform by writing Validation Policies (VPs) using a standard set of automated behavioral-trigger rules. Access Policies (APs) are implemented to gate products and services behind credibility thresholds and compliance requirements. This removes human bias and black-box interference from the trust process.
* **Decentralized Validation:** The three-set validator model ensures that no single entity controls the standard. Validation power is distributed across Organizational (for behavioral attestation), Peer (for social reputation), and Jury validators (for decentralized justice) to eliminate bias, identity recycling, and central points of failure.

\ <mark style="color:$info;">**Locked Modules:**</mark> The following modules represent the strategic growth of the protocol:

* **Proof of Liability:** Utilizing Ricardian Contracts, this module will cryptographically bind AI Agents to their human or organizational registrants, creating a legal and economic anchor for accountable, high-stakes autonomous operations.
* **Credibility-Weighted Governance:** A specialized governance framework where voting power is a function of both token stake and the participant’s credibility, ensuring that those with the highest verified reliability lead the protocol.
* **Dual Token Model:** The formal launch of the Tythe's native measure of credibility and its utility/governance tokens.
* **Credibility Licensing & Insurance:** A secure exchange for powering credibility data monetization, single-name credibility default swaps, and credibility default swap indices, turning credibility into a liquid financial asset class.



{% hint style="info" %}
#### Reader Note

To maintain accessibility for all audiences, we have refrained from using Tythe-native terminology on this canonical page where possible. To map Tythe-native terminology to specific protocol products, modules, and mechanics, please refer to the [Native Glossary](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/n9NH64V8Hfw4pxlNBmxl/~/edit/~/changes/27/the-standard-for-global-credibility/native-glossary).
{% endhint %}

</details>
