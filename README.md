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

Tythe is a decentralized orchestration layer designed to establish the first global standard for Assetized Credit. It serves as the foundational infrastructure for a risk-intelligent, borderless economy, empowering Humans and AI Agents with sovereign credit profiles that prove their financial reliability—their capacity to carry risk—without the friction of national borders, the risks of centralized data honeypots, or the opacity of legacy bureaus. For digital institutions, DeFi protocols, and global enterprises, Tythe provides the critical rails to scale operations by offloading risk-data liability, automating credit enforcement, and transforming static reliability signals into real-time, programmable assets.

<details>

<summary><strong>The Definition: What is Credit?</strong></summary>

In the Tythe ecosystem, Credit is not merely a number; it is a sovereign financial asset representing an actor's total reliability within the global economy.

Tythe Credit is the aggregated result of verified, real-time behavioral signals processed through the TCS-26 (Tythe Credit Standard 2026) engine. Unlike legacy models that equate credit solely with "debt history," Tythe defines credit as the capacity to carry and manage risk. This is quantified through two distinct but interconnected layers: the TCS Scoreand a suite of Granular Reliability Factors (GRFs).

**1. The TCS Score: Bias-Blind Reliability**

The TCS Score (7–100) is the protocol’s primary measure of Behavioral Reliability. To ensure total fairness and global inclusivity, the TCS Score is designed to be bias-blind:

* **Pure Behavior:** The engine does not intake employment status, income levels, or raw financial volumes (USD-equivalence) into the TCS calculation.
* **Reliability over Capacity:** It is a pure reflection of _how_ an actor behaves—their consistency in repayment, adherence to security protocols, and alignment with compliance standards.
* **Global Standard:** This allows a retail borrower and an institutional fund manager to be measured on the same scale of "Trustworthiness," independent of their net worth.

**2. The Granular Reliability Factors (GRFs): Capacity-Weighted Intelligence**

While the TCS Score measures intent, the GRFs (0.000–1.000) provide the "Economic DNA" required for institutional-grade underwriting. These factors account for Financial Capacity, proving an actor's reliability at scale:

* **Solvency & Liquidity:** Measures real-time capital efficiency, stablecoin cashflow, and balance maintenance (savings).
* **Borrower Integrity:** Tracks historical repayment reliability and settlement consistency across DeFi and tokenized debt markets.
* **Security & Compliance:** Evaluates the safety of financial execution (wallet security, audit-aligned interactions) and ZK-verified regulatory standing (KYC/AML/Proof of Humanity).
* **Asset Management:** Evaluates the quality of portfolio retention, including Real-World Asset (RWA) exposure, staking duration, and tokenized management.
* **Market Experience:** Analyzes the depth of participation in liquidity pools, trading volume, and "stickiness" (non-mercenary behavior) across execution venues.

The Tythe Credit Standard (TCS) and Granular Relibility Factors (GRFs) are designed to achieve comprehensive inclusivity, greater accuracy, and higher granularity for increased predictive power and a wider range of use cases.

{% hint style="info" %}
#### **Contextual Weighting: An Intelligent Scoring Standard**

While the TCS-26 is a universal standard, Tythe applies Contextual Weighting to ensure accuracy across diverse actors. The protocol recognizes that an AI Agent managing a treasury and a human retail borrower demonstrate reliability through different behavioral patterns. Tythe ensures credit is evaluated based on the verified impact within an actor's specific economic context—merging behavioral intent with financial capacity to create a 360-degree risk profile.
{% endhint %}

</details>

<details>

<summary><strong>The Problem:</strong> <strong>Why is Tythe necessary?</strong></summary>

The development of the Tythe Credit Standard is a direct response to the systemic failures and structural limitations of the financial models that preceded it. Traditional and early on-chain credit systems are no longer sufficient to underwrite the participants of a high-velocity, automated economy.

1. **Traditional Off-Chain Models:** Traditional credit relies on opaque scoring algorithms and centralized architecture that is defined by systemic inaccuracies, lack of transparency, and inherent biases.
   * **Security Risks:** Centralized PII storage creates massive single points of failure (e.g., the 2017 Equifax breach).
   * **Compromised Sovereignty:** Users have zero control over their data, and errors in reporting often take months of manual dispute to resolve.
   * **Jurisdictional Friction:** Credit intelligence is currently bound by national borders. A "Good" score in one country is functionally worthless the moment an actor crosses a border, trapping global liquidity.
   * **Reporting Lag:** Legacy reports are days out-of-sync with reality, often relying on low-latency snapshots. In a high-velocity market, this lag represents unacceptable risk.
   * **The AI Ceiling:** Biological-based identifiers (SSNs/Passports) cannot scale to underwrite AI Agents, effectively barring autonomous actors from participating in the global credit economy.
   * **Limited View of Creditworthiness:** Traditional scores do not consider income, employment history, or rental payments, potentially making millions of people "credit invisible".&#x20;
2. **Current On-Chain Models:** Early decentralized models improved output transparency but failed to solve the fundamental problem of identity integrity and opaque algorithmic scoring.
   * **Identity Recycling:** Most on-chain models remain tethered to disposable wallet addresses. Without an orchestrated identity layer, actors can "wash" a poor credit history by simply rotating to a new address, making long-term accountability impossible.
   * **Opaque Scoring:** Many DeFi credit protocols operate as "new bureaus," using closed-source scoring logic that lacks the multi-sector depth (RWA exposure, security audits, and compliance history) required for institutional-grade risk management.
   * **Sybil Vulnerability:** Without compliance and uniqueness anchors embedded into credit, on-chain systems remain vulnerable to coordinated manipulation, leading to chronic over-collateralization and capital inefficiency.
   * **Reporting Lag:** Legacy reports are days out-of-sync with reality, often relying on low-latency snapshots. In a high-velocity market, this lag represents unacceptable risk.
   * **The AI Ceiling:** Biological-based identifiers (SSNs/Passports) cannot scale to underwrite AI Agents, effectively barring autonomous actors from participating in the global credit economy.

{% hint style="danger" %}
#### The Result: Fear-Driven Financial Markets

* **In DeFi:** Protocols enforce extreme over-collateralization because they cannot verify counterparty reliability.
* **In TradFi:** Institutions are blocked from blockchain markets because they cannot verify compliance or credit history without exposing sensitive data.
* **In the Agent Economy:** AI Agents are treated as "bots" to be blocked rather than economic actors to be held liable.
{% endhint %}

</details>

<details>

<summary><strong>The Solution:</strong> <strong>How does Tythe work?</strong></summary>



1. **Identity:** This pillar orchestrates identity authentication, uniqueness, compliance, and aggregation. Utilizing did:cheqd as the anchoring layer (currently active on the cheqd testnet), Tythe enables its DIDs to function as sovereign, root keys that persist across jurisdictions and platforms.
2. **Data:** This pillar transforms raw behavioral signals into standardized, machine-readable outputs: 1-6 (Violation Codes), 7-100 (TCS Credit Score), and 0.000-1.000 (Granular Reliability Factors—GRFs). The protocol provides a Verifiable Receipt-based memory layer and institutional-grade, configurable reports (TCS Credit Reports and GRF Reliability Reports) where data remains private and permissions-based by default.
3. **Validation:** This pillar utilizes policy-as-code to allow institutions and protocols to automate attesting based on observed valuable behavior within their digital boundaries. Organizations define the parameters of "reliability," and the protocol handles the cryptographically secure verification of those actions.
4. **Enforcement:** Risk-Intelligent Gatekeeping This pillar empowers institutional participants to define access conditions and eligibility requirements using Policy-as-Code. These gates automatically permit or deny entry based on real-time TCS scores, GRFs, reports, and specific compliance checks. This ensures system privileges and financial products are gated by the highest quality of merit.
5. **Justice:** Credit data requires recourse for maximum accuracy. The Justice pillar utilizes Decentralized Juries—randomly selected, high-reliability participants—to review evidence-backed cases of misconduct and handle credit reporting disputes. This process protects the network by applying a status of unreliability (Violation Codes 1-6) to malicious identities, effectively flagging the root DID across the entire ecosystem.
6. **Governance:** A locked module to be activated post-mainnet. This pillar will transition the protocol’s parameters into the hands of a decentralized community of reliability weighted stakeholders. Tythe governance participants are selected to lead only their specific dimensions of operational expertise.
7. **Value:** A locked module to be activated post-mainnet. This pillar manages a dual token framework for ecosystem credit and incentives. Both tokens are utilized for governance weighting. The Tythe financial stack and capital programs are reserved for post-mainnet launch.

{% hint style="info" %}
#### Navigation Note

Tythe’s solutions are audience-tailored, currently enabling Individuals, Developers, and Institutions to interact with a unified foundational infrastructure. While all three entities share the same underlying fabric, they navigate Tythe’s 7 Pillars differently to leverage assetized credit in a privacy-preserving environment. To learn more about how currently supported audience groups interact with these pillars to achieve their goals, please refer to the \[Audience Orientation Guide].

* For Individuals
* For Developers
* For Institutions

\
Note: The framework to support assetized credit for AI Agent actors is a post-mainnet launch item. Click here to learn more about the how Tythe will power agentic commerce.
{% endhint %}



</details>

{% hint style="info" %}
#### Reader Note

To maintain accessibility for all audiences, we have refrained from using Tythe-native terminology on this canonical page where possible. To map Tythe-native terminology to specific protocol products, modules, and mechanics, please refer to the Native Glossary.
{% endhint %}
