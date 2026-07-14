---
description: Coming with Morpho Midnight. Not available at launch.
---

# Mandates & Limits

A mandate is the grant of authority a principal gives an agent. It defines exactly what the agent may do, and the contracts enforce it.

This is the difference between delegating to an agent and trusting one. A mandate is not a policy the agent is expected to follow. It is a boundary the agent cannot cross.

#### What a mandate contains

1. **Scope: what the agent may do.** Borrow. Repay. Post collateral. Adjust a position. Each permission is granted separately, so an agent authorized to top up collateral when a position weakens does not thereby gain the authority to borrow more.
2. **Size: how much.** A maximum borrowable amount, drawn from the principal's own credit envelope. An agent can never access more credit than its principal was underwritten for, and a principal may grant it less.
3. **Risk: how far.** A maximum loan-to-value the agent may borrow to, which can be set well below the principal's own limit. A borrower who has earned a 85% loan-to-value can cap their agent at 60%, keeping the efficiency they earned for their own decisions and giving the agent a conservative allowance.
4. **Time: for how long.** Mandates expire. An agent granted authority for a week holds it for a week.
5. **Revocation: at any moment.** The principal can withdraw the mandate immediately, without the agent's cooperation.

#### The limits are enforced, not trusted

Every limit above lives in the contracts. An agent that attempts to borrow beyond its size cap does not borrow beyond its size cap: the transaction fails.

This matters more than it might appear. The central fear about autonomous agents handling money is that the agent misbehaves, misunderstands, or is manipulated into an action its owner never wanted. That fear is well founded, and it is exactly why the mandate is a contract-level constraint rather than an instruction in a prompt.

The agent's own reliability is therefore not something Synclear needs to underwrite. A poorly built agent operating under a tight mandate can waste its principal's time and cost them interest. It cannot drain their account or borrow beyond what its principal authorized, because it does not have the authority to, and authority here is not a matter of intent.

#### The infrastructure

Agent mandates are not a Synclear invention. They rest on standards built for exactly this purpose.

* **ERC-8004** provides on-chain identity and reputation for agents, and was designed to link an agent's actions to a verified sponsor so that accountability survives autonomy. It was developed jointly by the Ethereum Foundation, MetaMask, Google, and Coinbase, and has been live on mainnet since January 2026.
* **Account abstraction** lets a wallet delegate narrow, scoped authority to an agent through session keys, so the agent operates on the principal's behalf without ever holding the principal's private key. Delegations can be issued for a single purpose and expire automatically.
* **Morpho Midnight** provides the lending markets themselves: fixed-rate, fixed-term, and permissioned at the market level, so a market can be restricted to verified principals and their authorized agents.

Synclear composes these rather than reinventing them, which is the same principle applied everywhere else in the protocol.

### Setting a mandate

{% stepper %}
{% step %}
#### **Be underwritten first**

A business passes KYB and is underwritten on its cash flow. An individual is verified and scored. This establishes the credit envelope, and it happens before any agent is involved.
{% endstep %}

{% step %}
#### **Register the agent**

The agent is registered against the principal's verified identity, so its actions are attributable.
{% endstep %}

{% step %}
#### **Grant the mandate**

The principal sets the scope, size, risk ceiling, and duration. Each is a hard limit, not a target.
{% endstep %}

{% step %}
#### **Monitor and revoke**

The agent's actions are visible on-chain and attributable to it. The mandate can be tightened or withdrawn at any point.
{% endstep %}
{% endstepper %}

### What a mandate does not do

* **It does not make the agent a borrower.** The loan belongs to the principal, and the principal repays it.
* **It does not transfer liability to the agent.** An agent acting within its mandate is acting for its principal, and the consequences are the principal's. See Accountability and Scoring.
* **It does not make the agent's decisions good ones.** A mandate constrains what an agent may do. It cannot make an agent wise. An agent that borrows to its permitted ceiling and then watches its collateral fall has done nothing it was forbidden to do, and its principal will bear the liquidation.

The mandate is a wall, not a supervisor. It defines the space within which an agent can act, and within that space the agent's judgement, and the principal's choice of agent, is what determines the outcome.
