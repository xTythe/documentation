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

# Governance Arm

The Governance Arm of Tythe DAO manages scoring parameters, formula upgrades, treasury allocation, and the overall direction of the protocol. It activates in V1.2 once the TYT token is live and the protocol has established a verifiable data foundation worth governing.

Governance is deliberately deferred from launch. Activating governance before meaningful protocol data exists would mean voting on parameters without evidence. Tythe governs on the basis of what the data shows, not what participants speculate.

***

#### TYT (The Protocol Token)

TYT is Tythe's governance token. It represents a stake in the protocol's future and the right to participate in its direction. TYT holders vote on protocol upgrades, fee parameters, new module activations, treasury allocations, and ecosystem proposals.

***

#### Dual-Track Voting Model

Tythe DAO operates two separate governance tracks. Each track governs a distinct set of decisions and requires a different combination of participation signals.

**Track 1: Formula Governance** \
Proposals affecting scoring parameters, formula weights, slash severity tables, CAVB classifications, and TCE standard upgrades. Voting on Track 1 requires both a minimum TCT threshold and TYT holdings. Among eligible voters, TYT holdings determine voting weight. Neither credential alone is sufficient. Participants must demonstrate both behavioral credibility and capital commitment to influence the scoring formula.

This prevents two failure modes simultaneously: wealthy actors cannot buy control of the formula that determines everyone else's creditworthiness, and low-capital participants with high credibility cannot make consequential formula changes without meaningful economic stake.

**Track 2: Protocol Governance** \
All other protocol decisions, such as fee parameters, new module activation, treasury allocation, ecosystem grants, integration approvals, and partnership ratification. Pure TYT-weighted voting.

***

#### Additional Notes

* Institutional DAO members are a distinct participant class within the Governance Arm. They are the only participants with visibility into exact formula weights (the sealed parameters that sit beneath the publicly disclosed formula structure).
* Changes to TCE scoring parameters, including tier weights, the historical lookback window, CAVB classifications, and slash severity tables — require a successful Track 1 governance proposal with a mandatory timelock before activation.
* Tythe DAO is designed to take on increasing responsibility as the protocol matures. At V1.2 activation, governance scope is limited to the parameters described above. As the protocol grows and the community demonstrates the capacity for responsible stewardship, governance scope will expand through successful proposals.
