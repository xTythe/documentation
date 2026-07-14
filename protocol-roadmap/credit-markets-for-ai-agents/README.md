---
description: Coming with Morpho Midnight. Not available at launch.
---

# Credit Markets for AI Agents

An AI agent can borrow from Synclear. It cannot borrow on its own account.

Every agent borrows as the authorized instrument of a verified principal: a business that has passed KYB and underwriting, or an individual who has been KYC verified and scored. The principal grants the agent a bounded mandate, the agent operates inside it, and the principal remains responsible for what the agent does within it. The agent is how the loan is operated. The principal is who the loan belongs to.

This is not a limitation imposed reluctantly. It is the only design under which agent credit is safe at all.

#### Why an agent is never an independent borrower

A person can hold one identity. A business can hold one legal registration. **A single operator can create a thousand agents in an afternoon.**

Every protection in on-chain credit assumes the borrower is a bounded, identifiable, accountable party. Isolation limits assume a borrower cannot simply become ten borrowers. Concentration caps assume that 5% of the fund lent to one borrower is 5% of the fund at risk, not 50% lent to one operator wearing ten faces. Scoring assumes a record belongs to someone who cannot abandon it and mint a new one.

Anonymous agent borrowing breaks all three at once. It is a Sybil attack with better branding.

Tying every agent to a verified principal restores each of those protections. The principal is the borrower, the principal's limits are the limits, and an operator who deploys fifty agents is still one borrower with one credit envelope.

#### The two paths

1. **A business deploys an agent.** The business passes KYB and is underwritten on its live cash-flow data, exactly as it would be if a human were borrowing. It then authorizes an agent to draw against its credit envelope: to top up working capital when cash runs low, to draw on a schedule, or to manage a position without a person in the loop.
2. **An individual deploys an agent.** The individual is verified and scored, earning a collateral discount on the loan-to-value they can borrow at. They then authorize an agent to operate within it: to manage collateral, to top up a position when its health falls, to borrow and repay within limits they set.

In both cases the credit decision is made about the principal, before any agent is involved. The agent inherits an envelope. It does not earn one.

#### The mandate is a constraint, not a promise

An agent operating for a Synclear borrower does not hold the keys to their account and a hope that it behaves. It holds a **mandate**: an on-chain grant of narrow, bounded, revocable authority.

The mandate specifies what the agent may do, up to what size, at what loan-to-value, and until when. Those limits are enforced by the contracts. An agent cannot exceed its mandate, so "the agent went rogue and borrowed everything" is not a risk Synclear has to price, in the same way that a card with a spending limit cannot be used beyond it.

The principal can revoke the mandate at any time.

This rests on infrastructure that now exists. ERC-8004, developed jointly by the Ethereum Foundation, MetaMask, Google, and Coinbase and live on mainnet since January 2026, provides on-chain agent identity explicitly designed to link an agent's actions to a verified sponsor. It composes with account abstraction, where a wallet delegates narrow, expiring authority to an agent that never holds raw private keys.

Full detail is on [Mandates and Limits](mandates-and-limits.md).

#### The agent's record is the principal's record

If your agent lets a position drift into liquidation, that liquidation appears on **your** credit history, not the agent's.

This follows from how liability actually works. When an agent acts within the authority its principal granted it, the principal bears the consequences. You chose the agent, you set its mandate, and you delegated the decision. Its conduct is your conduct.

The incentive this creates is the correct one. A borrower who deploys a careless agent pays for it in their own score, their own collateral requirement, and their own rate. Nobody will delegate credit decisions to an untested agent when the cost of its mistakes lands on their own borrowing terms.

Full detail is on [Accountability and Scoring](accountability-and-scoring.md).

#### Why this is worth building

Agents are already transacting. Agentic commerce reached roughly $8 billion in transaction value in 2026, around 40% of commercial applications now embed autonomous agents, up from under 5% a year earlier, and agent-run DeFi already accounts for a meaningful share of the AI-crypto market.

What those agents cannot do is borrow. They can hold a wallet, pay for services, and execute strategies, but no lending market can tell the difference between an agent backed by a verified business and an anonymous script, so none of them can safely extend credit to either.

Synclear can, because it already underwrites the principal. The credit infrastructure agents need is not a new kind of credit. It is ordinary credit, extended to a verified borrower, operated by a bounded instrument on their behalf.

#### In this section

* [Mandates and Limits](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/45/protocol-roadmap/credit-markets-for-ai-agents/mandates-and-limits), how a principal authorizes an agent and how the limits are enforced
* [Accountability and Scoring](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/45/protocol-roadmap/credit-markets-for-ai-agents/accountability-and-scoring), who is liable, and how an agent's conduct affects its principal's credit
