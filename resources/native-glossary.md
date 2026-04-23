# Native Glossary

Reading the glossary carefully. Changes needed:

* CEW renamed to CAL throughout
* CEW definition updated to reflect new architecture
* Enhancement, Enforcement, Blocker definitions updated to reference CAL not CEW
* CEW Fee Switch renamed to CAL Fee Switch and updated
* Blocker definition updated — CAL now reverts directly with `BlockedWallet()`, protocol does not handle the revert
* CDX renamed to Credit Data
* TYT entry — Credit Voucher reference needs removing (deprioritized)
* CAQB renamed to CAQB (was CAVB in older docs, already correct here)
* Add missing terms: CAL, tMVV/rMVV already present, Tythe Prime missing
* Agent instructions block removed

***

## Native Glossary

The canonical definitions for every term in the Tythe protocol.

***

**Protocol**

| Term               | Definition                                                                                                                                                                                                                                                                                                 |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Tythe Protocol** | The neutral, decentralized infrastructure for credit. Provides the identity (Credit Profile), intelligence (TCT and MVV), integration (CAL), and data (Credit Data Exchange) layers required to transform on-chain behavioral data into verifiable, actionable creditworthiness.                           |
| **Tythe Prime**    | The capital efficiency space built natively on the Tythe Protocol stack. Accessible to Prime (670+ TCT) and Superprime (780+ TCT) participants only. Houses three vault types: Prime Efficient, Collateral Maximization, and Default Insurance.                                                            |
| **TCE Standard**   | **Tythe Credit Enhancement Standard.** The canonical framework defining how behavioral telemetry and capacity metrics are scored and tokenized into a machine-enforceable financial risk signal. The current live model is TCE-26.                                                                         |
| **TCE-26**         | The protocol's launch scoring model. Defines the formula structure, input weights, band thresholds, and parameter set used to calculate TCT scores. Future models are activated only via a successful Tythe DAO governance proposal.                                                                       |
| **TYT**            | **The Tythe protocol token.** Used for Tythe DAO governance and protocol incentive alignment. Launches in V1.2.                                                                                                                                                                                            |
| **CAQB**           | **Collateral Asset Quality Benchmark.** A risk-weighting index that categorizes collateral assets from AAA to CCC quality tiers based on 180-day realized volatility and secondary market depth. Governs both the Volatility Quotient component of the TCT score and the MVV ceiling for a given position. |
| **Tythe DAO**      | The decentralized governance and arbitration layer of the protocol. Operates two arms: the Justice Arm (dispute resolution) and the Governance Arm (formula and parameter governance). Activates in V1.2.                                                                                                  |

***

**Identity**

| Term                          | Definition                                                                                                                                                                                                                                                                                                                     |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Credit Profile (CEP)**      | The sovereign financial identity layer. Anchored on the `did:cheqd` network, the Credit Profile is a permanent, privacy-preserving financial identity that unifies a participant's wallets, credentials, attestations, and credit history into one resolvable profile. Built by individuals. Resolved and verified by markets. |
| **DID-Linked Resource**       | Any on-chain resource (wallet addresses, EIP-712 attestations, TCT balance, verifiable credentials) attached directly to a participant's DID. Creates a unified, resolvable financial profile.                                                                                                                                 |
| **Proof of Personhood (PoP)** | An optional biometric-anchored credential (via World ID or equivalent) attached to a Credit Profile. Grants a fixed +5 TCT boost and strengthens Sybil resistance.                                                                                                                                                             |
| **zk-KYC**                    | Zero-knowledge identity verification and sanctions screening provided via Billions. Processed entirely via zero-knowledge attestation. No raw identity data is held by the protocol at any point.                                                                                                                              |

***

**Intelligence**

| Term                  | Definition                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **TCT**               | **Tokenized Creditworthiness.** A non-transferable ERC-20 token representing a participant's credit character score (300-850). A pure behavioral signal earned through seven inputs and lost through verified negative events. The primary credit signal used to price risk, apply enhancements, and enforce limits across integrated markets.                                                                                                  |
| **tMVV**              | **Per-transaction credit limit.** The maximum value-based enhancement CAL can apply on any single transaction, expressed in USD. A hard ceiling per transaction. Enhancements apply up to tMVV. Transactions above tMVV proceed at standard terms for the remainder. Derived from Capital Capacity Markers and updated at Refresh.                                                                                                              |
| **rMVV**              | **30-day rolling credit limit.** The total value-based enhancement budget across all transactions in a 30-day window. rMVV = tMVV x 10. Depletes in real time as enhancements are applied across all integrated markets. Resets automatically every 30 days from first consumption. When rMVV is exhausted, no further value-based enhancements until the window resets.                                                                        |
| **Staged Score**      | A participant's current off-chain creditworthiness, continuously computed by the protocol as behavior changes. Always current. Distinct from the on-chain TCT balance, which updates only on Manual Refresh.                                                                                                                                                                                                                                    |
| **Manual Refresh**    | The participant-initiated process of tokenizing their staged score as updated on-chain TCT, tMVV, and rMVV values. Triggered via the Tythe Dashboard. Participant pays gas.                                                                                                                                                                                                                                                                     |
| **Auto-Slash**        | The protocol's automated enforcement mechanism. Upon a confirmed nEvent, the protocol immediately reduces the participant's on-chain TCT balance. Slash severity is determined by the participant's percentile rank within the relevant nEvent label's spectrum. Gasless.                                                                                                                                                                       |
| **Drops and Buckets** | The asymmetric mechanic governing TCT movement. Positive score changes accumulate gradually in drops, earned through consistent, responsible behavior over time. Negative changes are applied in buckets: swift, significant reductions triggered by nEvents. TCT is slow to gain and fast to lose.                                                                                                                                             |
| **nEvent**            | **Negative Event.** A verifiable on-chain credit deterioration event (Liquidation, Default, Exploit, Mercenary, Informed, or Whale) detected, classified, and ranked by the Relay Emitter. Where applicable, nEvents trigger an automated enforcement response.                                                                                                                                                                                 |
| **Relay Emitter**     | The off-chain ML-powered intelligence layer built on gradient boosting models (XGBoost and LightGBM). Continuously monitors on-chain behavioral patterns, classifies negative credit events, and ranks each participant within their label's spectrum by severity. Percentile rank determines Auto-Slash severity. Ranked nEvent labels are broadcast to institutional subscribers and consumed internally by the deterministic scoring engine. |

***

**Integration**

| Term               | Definition                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **CAL**            | **Credit Adjustment Layer.** A smart contract primitive that any protocol builds into their transaction flow for automatic, credit-differentiated adjustments based on a participant's TCT score. Applies two independent adjustments at transaction time: a value track (MVV-governed, applies to dollar-denominated parameters) and a rate track (unconstrained, applies to percentage-based parameters). Three integration paths available: native, advisory, and direct read. |
| **Enhancement**    | The CAL action applied to Excellent and Very Good bracket participants. Delivers upgraded capital terms up to the participant's tMVV and rMVV limits on the value track. Rate track enhancements are governed by TCT bracket only with no MVV cap. Every value-based Enhancement depletes the participant's rMVV by the enhancement amount.                                                                                                                                       |
| **Enforcement**    | The CAL action applied to Fair and Poor bracket participants. Applies tighter capital terms proportional to the participant's bracket on both tracks. Does not deplete rMVV.                                                                                                                                                                                                                                                                                                      |
| **Block**          | The CAL action applied to Flagged (score 0) participants. CAL reverts directly with `BlockedWallet()`. Free on-chain. No fee, no counter.                                                                                                                                                                                                                                                                                                                                         |
| **CAL Fee Switch** | CAL launches fee-free. When activated by the Tythe DAO, a flat 0.07% Enhancement fee is collected on-chain from the borrower wallet at transaction time. Enforcement actions are tracked via an on-chain counter and billed off-chain monthly to the integrated market. Block actions are always free.                                                                                                                                                                            |
| **isInternal**     | An immutable flag set at market registration that determines the CAL integration pathway. Internal markets (Tythe Prime) have value track enhancements capped at min(tMVV, availableRMVV, transactionValue) and deplete rMVV on every Enhancement. External markets have no MVV cap and never deplete rMVV. Cannot be changed after registration.                                                                                                                                 |

***

**Data**

| Term                           | Definition                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Credit Data Exchange (CDX)** | A module enabling consent-gated, order-specific sale of verified credit data from individuals to institutional buyers. Buyers list dataset orders with eligibility criteria, anonymity levels, and payout per report. Tythe compiles and delivers at minimum fill. No individual's data is accessed, compiled, or delivered without explicit, order-specific opt-in. _(V3)_ |
| **Dispute Settlement**         | The decentralized arbitration process handled by the Tythe DAO Justice Arm. Participants stake TCT to raise a dispute. AI Clerks prepare evidence briefs from on-chain data. A human jury drawn from the disputant's TCT band delivers the verdict. Stake is burned if the slash is upheld and returned in full if overturned.                                              |
