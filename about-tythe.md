# About Tythe

Tythe is the neutral, decentralized protocol for credit. We provide the infrastructure to transform behavioral data into verifiable creditworthiness, giving every participant in the decentralized economy a smarter, fairer way to access and deploy capital.

***

#### The Problem

Credit, in its current form, is reaching its limits.

* **In Traditional Finance**, credit scoring is a black box. Opaque, non-portable, and owned by institutions. Users are a passive subject of their own financial data, stored in centralized databases they cannot control and cannot fully trust.
* **In DeFi and Crypto Markets**, the solution to not trusting anyone was to demand everything upfront. To borrow $1, users lock up $1.50. Over-collateralization is capital trapped; it protects the protocol but prevents real financial growth.
* **For Institutions and RWA Platforms**, the demand for credit intelligence is real, but the path to it is blocked. Handling raw private user data creates legal exposure. Existing solutions force a choice between compliance and utility.
* **For AI Agents**, the problem is structural. High-reputation autonomous agents are becoming primary economic actors, but they have no standardized way to prove that reputation or access credit. They operate on 100% upfront capital, regardless of their proven performance.

The result is the same across all four: capital locked behind gatekeepers, inefficiency baked into the system, and no portable standard for financial trust.

***

{% hint style="success" %}
#### **Why Tythe Works Where Others Have Failed**

Every previous attempt at decentralized credit made the same mistake: offering credit intelligence to institutions and expecting them to absorb the risk of default in return. No rational capital allocator accepts that trade.

Tythe does not ask institutions to change their risk appetite. The primary product is better capital terms on existing collateralized positions; credit intelligence that makes deals more competitive, not more dangerous. Where undercollateralized lending exists in the protocol, it is only possible through Credit Enhancement Vaults, where capital backs capital: risk is distributed across LPs who opt in explicitly for yield and risk premiums, never transferred silently to institutions.

The protocol coordinates capital. It does not gamble with it.
{% endhint %}

***

#### The Solution

Tythe builds the missing layer; a shared, verifiable standard for creditworthiness that works across DeFi, RWAs, digital markets and institutions, and AI networks.

{% hint style="info" %}
#### **What is Credit Enhancement?**&#x20;

Credit enhancement is the process of leveraging a verified creditworthiness (or financial reputation) to access better capital terms — lower interest rates, reduced fees, optimized borrowing limits, increased deposit yields, or tighter spreads; it makes capital offers risk-tailored and more competitive for all.
{% endhint %}

{% stepper %}
{% step %}
**Identity Layer&#x20;**_**(V1.1)**_

**Credit Enhancement Profile (CEP):** A portable, user-owned credit profile anchored on the did:cheqd network. The CEP aggregates on-chain wallet history and zkTLS-verified off-chain financial data into a single sovereign identity without exposing raw data at any point.
{% endstep %}

{% step %}
**Intelligence Layer&#x20;**_**(V1.1)**_

* **Tokenized Creditworthiness (TCT):** A TCT score (300–850) is a real-time, non-transferable ERC-20 token representing financial reliability. Embedded in its metadata is the Maximum Vouchsafed Value (MVV); the protocol's assessed credit limit for the position. TCT is earned in drops and lost in buckets, mirroring how trust actually works in the real world.
* **Relay Emitter:** The AI-powered Relay Emitter monitors the lifecycle of negative credit events (nEvents); Liquidations, Defaults, Exploits, and more. It identifies behavioral patterns, generates event labels, and broadcasts real-time risk-alpha to institutional subscribers. The Relay Emitter informs and labels. Scoring is handled separately by a deterministic, auditable formula.

> **Credit Vouchers (V1.2):** Verified banks, fintechs, funds, merchants, and AI networks vouch for participants by issuing on-chain EIP-712 attestations based on their internal due diligence or performance logs. Vouching institutions stake TYT protocol tokens, putting skin in the game on the accuracy of every voucher they issue. Credit Vouchers onboard after initial protocol traction, as institutional partners validate the live system before committing.
{% endstep %}

{% step %}
**Integration Layer&#x20;**_**(V1.1)**_

**Credit Enhancement Wrapper (CEW):** The on-chain logic proxy that puts TCT to work. The CEW intercepts financial transactions and applies credit signals in real time, unlocking rate discounts, limit boosts, or risk enforcement depending on the participant's score. This is where creditworthiness becomes a live financial tool.
{% endstep %}

{% step %}
**Justice Layer&#x20;**_**(V1.1)**_

**Tythe DAO (Justice Arm):** Handles disputed scores and contested slashes under the protocol's fixed launch formula. To raise a dispute, participants stake a protocol-defined amount of TCT as a good faith deposit. If the Justice Arm rules the slash was valid, a portion of the staked TCT is burned. If the dispute is upheld, the full stake is returned. AI clerks prepare evidence briefs from on-chain data; human juries drawn from the same TCT band as the disputant hear and resolve each case. Disputes at band boundaries are heard by mixed juries from both adjacent bands.
{% endstep %}

{% step %}
**Governance Layer&#x20;**_**(V1.2)**_

**Tythe DAO (Governance Arm):** Manages scoring parameters, formula upgrades, and the TYT token. Governance activates in V1.2 once the TYT token is live and initial protocol data has given the community something real to govern. Formula weights are visible to institutional DAO members only, preventing gaming while enabling decentralized oversight.
{% endstep %}

{% step %}
**Liquidity Layer&#x20;**_**(V2)**_

**Credit Enhancement Vaults (CEV):** Intelligence-optimized ERC-4626 vaults where LPs provide collateral top-offs to back TCT-verified borrowers. CEVs are the only module enabling undercollateralized lending, where risk is distributed across LPs who opt in for yield and premiums. Launching after V1 scoring data has matured and the protocol has established a verifiable track record.

> **Agentic Credit (V2):** Allowing verified AI agents to leverage execution history for protocol-backed credit lines is on the Tythe roadmap. Details in the [roadmap section](resources/roadmap-modules/).
{% endstep %}

{% step %}
**Data Layer&#x20;**_**(V2)**_

**Credit Data Licensing (CDL):** Participants choose to anonymize and license their credit data (to institutional researchers, model builders, and AI engineers) and are directly compensated for it. Tythe takes a platform cut. The participant keeps the rest. The first protocol to flip the credit bureau model in the user's favor.
{% endstep %}
{% endstepper %}
