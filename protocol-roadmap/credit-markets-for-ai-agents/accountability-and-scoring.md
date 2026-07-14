---
description: Coming with Morpho Midnight. Not available at launch.
---

# Accountability & Scoring

If your agent is liquidated, you are liquidated. If your agent repays well, you repay well. An agent's conduct is its principal's conduct, and Synclear scores it that way.

#### Liability follows authority

The rule is the one that governs delegation everywhere: **an agent acting within the authority it was granted acts for its principal, and the principal bears the consequences.**

This is how liability for autonomous agents is already understood. Where an agent acts on behalf of a principal, responsibility turns on whether the agent acted within its authority, and whether the outcome followed from the agent's own conduct or from the principal's instructions.

Synclear resolves this cleanly, because the authority is not a matter of interpretation. The mandate is enforced by the contracts. An agent literally cannot act outside its authority, so every action an agent takes is, by construction, an action its principal authorized.

There is no category of "the agent did something it was not allowed to do." If it was not allowed, it did not happen.

#### The consequences land on the principal

* **The debt is the principal's.** The agent borrows against the principal's envelope, and the principal repays.
* **The collateral is the principal's.** If a position is liquidated, the principal's collateral is sold.
* **The record is the principal's.** A liquidation caused by an agent appears in the principal's Historical Harm, weighted by severity and recency exactly as any other liquidation would be. It reduces their score, tightens their collateral requirement, and raises their rate.
* **The recovery is against the principal.** For a business borrower, KYB binds the loan to a legal entity, and a default is enforceable against that entity. An agent is not a shield.

#### Why this design

The alternative is to let an agent hold its own credit record, separate from whoever deployed it. That fails immediately.

An operator could deploy an agent, borrow, default, abandon the agent, and deploy another. The record would attach to a wallet that costs nothing to discard, which is not a credit history but a costume. And it would put the loss on the lender, who has no one to pursue.

Attaching the record to the principal makes it real. A principal cannot abandon their identity: a business has a legal registration, an individual has a verification, and their score is attached to that. Delegating to an agent does not launder the consequences.

#### The incentive this creates

**You will not deploy a careless agent, because you pay for its carelessness.**

If your agent borrows to the top of its permitted loan-to-value and then fails to respond as collateral falls, you are liquidated, and your Historical Harm records it. If your agent tops up diligently whenever a position weakens, that shows up in your Operator Quality, which is the heaviest signal in the model, and your terms improve.

The behaviour Synclear rewards in a human borrower is exactly the behaviour it rewards in an agent, because it is scoring the same account. This is deliberate. Synclear does not need to certify agents, audit their code, or rank them. It needs only to ensure that whoever deploys one has skin in the game, and the score does that.

Principals will select their agents carefully because the cost of a bad one lands on their own borrowing terms. That is a stronger discipline than any approval process Synclear could run.

#### Setting a conservative mandate is a protection

A principal is not obliged to give an agent everything they are entitled to.

A borrower who has earned an 85% loan-to-value can cap their agent at 60%. The agent then operates with a wide safety buffer, and the principal keeps their full efficiency for decisions they make themselves. If the agent misjudges, the buffer absorbs it, and the position is not liquidated.

This is the practical answer to agent risk, and it is available to every borrower: **grant the agent less rope than you have.**&#x54;he mandate is the lever, and it is entirely in the principal's hands.

#### What Synclear does not do

* **Synclear does not score agents.** Creditworthiness belongs to the principal. An agent's on-chain reputation may inform a principal's choice of which agent to trust, but it does not create a credit line, and a well-reputed agent deployed by an unverified operator still cannot borrow.
* **Synclear does not certify agents.** No agent is approved, audited, or endorsed by the protocol. The choice of agent is the principal's, and so are the consequences.
* **Synclear does not accept "the agent did it" as a defence.** An agent acting within its mandate acted for you. The mandate is always yours to set.
