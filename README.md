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

Tythe is a decentralized orchestration layer designed to establish the first global standard for assetized credibility. It serves as the foundational infrastructure for a risk-intelligent, borderless economy, empowering humans and AI agents with a purpose-built credibility profile that proves their reliability—their ability to carry risk—without limiting the effectiveness of their profile to a single jurisdiction, compromising their privacy, or relying on centralized intermediaries. For digital institutions, DeFi protocols, DAOs, and cross-sector applications, Tythe provides the critical rails to scale operations by offloading risk-data liability, automating risk enforcement, and going beyond proof of personhood risk-management with verifiable, real-time intelligence.

<details>

<summary><strong>The Definition: What is Credibility?</strong></summary>

In the Tythe ecosystem, "Credibility" is the asset capable of representing an actor's total multi-dimensional reliability. It serves as the aggregated result of verified behavioral signals spanning across five metrics, of which traditional "Creditworthiness" is a sub-component of the Financial Reliability metric:

* **Compliance&#x20;**_**Reliability Metric**_**:** Verifies adherence to regulatory frameworks. This covers Proof of Humanity/KYC/AML status, jurisdictional eligibility, and sanction-list screening. It ensures that actors meet rigorous compliance standards for institutional interaction without ever exposing sensitive PII to the network.
* **Financial&#x20;**_**Reliability Metric**_**:** Measures total solvency and capital efficiency. This includes verified income and employment, historical repayment reliability, cashflow, balance maintenance, and granular DeFi activity (lending, borrowing, staking, LP positioning, and trading). It further accounts for tokenized asset experience—including Real-World Asset (RWA) exposure, portfolio management, liquidity depth—incorporating and superseding traditional creditworthiness.
* **Governance&#x20;**_**Reliability Metric**_**:** Evaluates the quality of participation within decentralized structures. This tracks on-chain voting history, proposal frequency, delegation reliability, and alignment with protocol-specific standards, distinguishing active, value-aligned contributors from passive or extractive actors.
* **Security&#x20;**_**Reliability Metric**_: Assesses the technical and operational integrity of an actor. For developers, this includes smart contract authorship and audit history; for operators, it monitors validator uptime, slashing history, and secure key management behavior. This metric ensures of technical capabilty and soundness.
* **Sustainability&#x20;**_**Reliability Metric**_**:** Tracks alignment with ESG (Environmental, Social, and Governance) initiatives. This includes participation in carbon and renewable energy markets, sustainability-linked finance, and social impact programs, rewarding actors whose behavioral data reflects long-term environmental and social responsibility.

<figure><img src=".gitbook/assets/Image 1-25-26 at 10.36 PM.png" alt=""><figcaption></figcaption></figure>

Credibility is a standard designed to achieve comprehensive inclusivity, greater accuracy, and higher granularity for increased predictive power and a wider range of use cases.

{% hint style="info" %}
#### Multi-Dimensional Credibility: The Architecture of Purpose-Driven Profiles

The multi-dimensional nature of credibility in Tythe is not a "one-size-fits-all" umbrella model. Tythe does not mandate high-volume participation across all five metrics to achieve a valid credibility standing. Instead, this architecture is designed for purpose-driven profile building.

We recognize that different humans and AI agents have distinct operational fields; a developer may anchor their identity in Security, while a delegate focuses on Governance. Credibility is determined by verified impact within an entity's specific field of operation.
{% endhint %}

</details>

<details>

<summary><strong>The Problem:</strong> <strong>Why is Tythe necessary?</strong></summary>

The development of the Tythe standard is a response to the systemic failures and limitations of the models that preceded it.

* **Traditional off-chain models (for creditworthiness):** \
  Rely on black-box algorithms and centralized bureaus that store sensitive PII leading to single point failures (like Equifax 2017, where a single breach exposed the data of 147 million people). These systems also suffer from jurisdictional friction (intelligence is limited by national borders) and lagging reports (these can be days or even weeks out-of-sync with reality) that compromise user sovereignty and impose an "AI ceiling," effectively excluding autonomous agents and millions of "thin-file" humans while trapping global liquidity.
* **Current on-chain models (for creditworthiness):** \
  Improve transparency but remain tethered to histories of disposable wallet addresses. Without an orchestrated identity layer, they are highly vulnerable to Sybil manipulation and wallet recycling, failing to provide the long-term accountability or multi-sector depth required for institutional risk management.

</details>

<details>

<summary><strong>The Solution:</strong> <strong>How does Tythe work?</strong></summary>

Tythe’s architecture is designed to be audience-tailored, enabling Individuals, Developers, AI Agents, and Organizations to interact with the protocol’s foundational infrastructure to achieve specific operational goals. While all entities share the same underlying fabric, they navigate Tythe’s 7 Pillars differently to leverage assetized credibility in a privacy-preserving environment.

**The 7 Pillars of Credibility**

1. **Identity:** The foundation of the network. This pillar orchestrates identity authentication, uniqueness, compliance, and aggregation. Utilizing self-soveriegn, decentralized identities on the `did:cheqd network` as the anchoring layer (active on the cheqd testnet during Tythe testnet), Tythe enables its DIDs to function as universal, sovereign keys that persist across jurisdictions and platforms.\
   &#xNAN;_&#x4E;ote: AI Proof of Liability (Legal-grade) module is a roadmap item._
2. **Data:** This pillar transforms raw behavioral signals into standardized, high-fidelity, machine-readable outputs for risk-intelligence: 1–6 (Violation Codes), 7–100 (Credibility Score), and 0.000–1.000 (Metric Reliability Factors—granular scoring across Tythe's 5 metrics). To support institutional decision-making, Tythe generates audit-grade Credibility Reports (available in configurable metrics, timeframe, and depth) that provide verifiable, privacy-preserving summaries of an actor’s profile. The protocol provides a Verifiable Receipt (VR)-based memory layer where data remains private and permissions-based by default, ensuring that sensitive evidence is never exposed without authorization.\
   &#xNAN;_&#x4E;ote: Advanced non-custodial upgrades for memory ledgers is a roadmap item._
3. **Validation:** This pillar utilizes policy-as-code to allow organizations to automate attesting on observed valuable behavior within their digital boundaries. It also facilitates credibility transfers, enabling peer-to-peer validation where actors can vouch for the performance of other actors, with built in manipulation-resistance systemic safeguards.
4. **Enforcement:** Enforcement empowers institutional participants to define access conditions and eligibility requirements using policy-as-code, these gates automatically permit or deny entry based on real-time credibility scores, metric reliability factors, reports, and specific compliance checks. This ensures system privileges and products across multiple digital platforms are gated by the highest quality of merit.
5. **Justice:** Credibility requires recourse. The Justice pillar utilizes Decentralized Juries—randomly selected, high-credibility participants—to review evidence-backed cases of misconduct and issue binding verdicts. This process protects the network from systemic abuse by applying a status of unreliability (using the 1-6 Violation Codes) to malicious identities, effectively blacklisting the root DID across every linked data aggregator.
6. **Governance:** A locked roadmap module to be activated post-mainnet. This pillar will transition the protocol’s parameters into the hands of a decentralized community of "high-credibility" stakeholders. Tythe governance participants are weighted to lead only the pillars associated with their specific dimensions of operational expertise.
7. **Value:** The economic layer of credibility. This pillar manages the Dual-Token Framework (TCT and TYT) for ecosystem credibility and incentives—both of which contribute to governance weighting. While the core tokens launch during Testnet v1.2, Tythe's full financial stack and economic programs are reserved for post-mainnet deployment.

{% hint style="info" %}
#### Reader Note

To maintain accessibility for all audiences, we have refrained from using Tythe-native terminology on this canonical page where possible. To map Tythe-native terminology to specific protocol products, modules, and mechanics, please refer to the [Native Glossary](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/n9NH64V8Hfw4pxlNBmxl/~/edit/~/changes/27/the-standard-for-global-credibility/native-glossary).
{% endhint %}

</details>
