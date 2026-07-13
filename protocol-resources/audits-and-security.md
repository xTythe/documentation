# Audits & Security

The smart-contract layer is the custody layer. Synclear's contracts hold user funds directly, so their security is not a feature of the protocol, it is the protocol.

***

#### Audits

Every Synclear contract is audited by an independent security firm before it handles user funds. Reports are published in full, including findings that were raised and how each was resolved.

| Contract                                  | Auditor | Report |
| ----------------------------------------- | ------- | ------ |
| _Published on completion, before mainnet_ |         |        |

An unaudited contract does not hold user capital. There is no exception to this for a new product, a fast-follow, or an upgrade.

***

#### Engineering standard

Contracts are written to favour clarity and established patterns over cleverness. Complexity is where exploits live, and a contract that is simple enough to be fully understood by a reviewer is worth more than one that is elegant and opaque.

Synclear's contracts are developed under test-driven development, with full test coverage and static analysis as a condition of deployment rather than an afterthought.

***

#### Live protections

**Circuit breakers.** Defined thresholds halt protocol activity automatically when conditions move outside expected bounds. A breaker firing stops the protocol; it does not require a human to notice first.

**Oracle redundancy.** Prices are drawn from multiple independent sources. No single feed can misprice the system, and a feed that diverges from its peers is disregarded rather than acted upon. Oracle manipulation is one of the most common attack vectors in DeFi, and a single price source is the vulnerability that makes it work.

**Position limits.** Strategy exposure is bounded by protocol-defined limits that the algorithmic manager cannot exceed. The limits are enforced in the contracts, not by policy.

**Multi-venue and multi-custodian.** No single venue or custodian failure can halt the protocol or strand its backing.

***

#### Insurance

Every product that holds capital carries smart-contract insurance against a technical failure or exploit, provided by Chainproof and Nexus Mutual. Chainproof is a regulated underwriter, and claims are adjudicated by independent technical investigation rather than by a vote of people whose capital would pay the claim.

Insurance is not a substitute for security. It is what stands behind security when security fails, which is the only honest way to think about it.

***

#### Contracts

| Contract                  | Network | Address |
| ------------------------- | ------- | ------- |
| _Published at deployment_ |         |         |

***

#### Reporting a vulnerability

If you have found a vulnerability in a Synclear contract, report it to **\[security contact]** rather than disclosing it publicly. Synclear runs a bug bounty, and a researcher who reports responsibly is paid for it.
