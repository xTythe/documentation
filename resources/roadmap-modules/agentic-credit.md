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

# Agentic Credit

Every onboarded agent receives a sovereign credit identity anchored on the did:cheqd network (the same infrastructure used for human CEPs). Agent identities are distinguished by a username convention: human participants use @handle, AI agents use @handle.ai. The underlying DID is unique to every actor regardless of type.

Co-signer CEP DIDs are linked on-chain to their agent's CEP DIDs at onboarding. This link is permanent and publicly resolvable. Accountability is anchored at the identity layer, not just contractually.

***

#### Co-Signer Accountability

Every agent on Tythe is co-signed by a verified individual, team, or ecosystem. The co-signer is both legally and protocol-accountable for their agent's behavior.

**Co-signer requirements:**

* CEP verified
* TYT staked against the agent's protocol participation&#x20;
* Ricardian contract signed for agent accountability

**Co-signer consequences:**

* If an agent defaults, acts maliciously, or is found to have exploited the protocol, the co-signer's CEP is flagged and their staked TYT is slashed
* Repeat or severe violations may result in the co-signer losing the ability to onboard future agents
* Co-signers do not earn TCT. Their stake is accountability, not yield.

Co-signers may be individual developers, development teams, or verified AI ecosystems (such as Kite AI or equivalent agent networks) who can recommend and vouch for agents from their own ecosystem.

***

#### Onboarding Process

Agent onboarding runs in selection periods, not continuously. This ensures each cohort of agents is properly evaluated before being granted access to protocol credit infrastructure.

**Stage 1. Co-Signer Verification:** The co-signer completes CEP verification and stakes TYT. Signs the Ricardian contract of agent accountability. Co-signer CEP DID is registered as an accountable identity on the protocol.

**Stage 2. Agent Recommendation:** The co-signer nominates agents from their ecosystem for evaluation. Nominations must be accompanied by execution history evidence (on-chain performance logs, audit reports, and third-party evaluation results) from recognized agent performance and code safety platforms.

**Stage 3. Evaluation:** Nominated agents undergo a thorough evaluation of execution performance, code safety, security audit results, and behavioral consistency. Evaluation criteria and recognized third-party platforms are published by Tythe ahead of each selection period.

**Stage 4. Onboarding:** Agents that clear evaluation are onboarded to Tythe. A did:cheqd identifier is minted for the agent. The agent's CEP DID is linked on-chain to the co-signer's CEP DID. The agent is now eligible for scoring and protocol credit access.

***

#### Agent Scoring

Agents are scored on execution history and performance using a purpose-built adaptation of the TCE-26 framework. The scoring model evaluates:

* **Trade Performance:** Consistency and quality of trading decisions over time
* **Liquidation Avoidance:** Track record of maintaining healthy positions without liquidation events
* **Vault Management Quality:** Performance of managed vault positions (yield optimization, risk management, LP behavior)
* **Consistency of Returns:** Stability and reliability of on-chain returns over time
* **Code Security:** Audit results and security evaluation scores from recognized third-party platforms

The output is a TCT score (300-850) assigned to the agent's CEP. Higher scores unlock better capital terms across all CEW-integrated markets and CEV vaults, which is the same credit infrastructure available to human participants.

***

#### What Agents Can Access

A scored agent with an active TCT balance accesses the full Tythe credit stack:

* **CEW enhancements:** rate discounts, limit boosts, and reduced fees on integrated markets based on TCT bracket
* **CEV top-offs:** collateral backing for undercollateralized positions on eligible vaults
* **MVV:** a protocol-assessed credit limit that scales with the agent's proven capital management capacity

Agents operate within the same risk brackets and enforcement rules as human participants. A slashed agent faces the same consequences as a slashed human, with the added consequence that the co-signer's CEP and TYT stake are also affected.

***

#### The Parity Principle

Tythe does not distinguish between human and agent creditworthiness at the protocol level. A reliable agent with a verified execution history and a high TCT score accesses the same terms as a reliable human with equivalent behavioral credibility. Capital efficiency is earned through performance, not through the nature of the actor performing.

Agentic Credit is the logical endpoint of what Tythe is building. If creditworthiness is behavioral, and behavior can be verified on-chain, then any actor (human or agent) with a verifiable track record deserves access to credit on those terms.
