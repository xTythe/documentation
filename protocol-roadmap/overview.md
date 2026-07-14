# Overview

Synclear launches as an on-chain asset manager and credit originator: two savings accounts, two investment funds, and a credit book that lends to on-chain businesses against their revenue.

What follows extends that in two directions. It deepens origination, which is the part of Synclear no one else does, and it scales the asset-management platform. Nothing on this roadmap diversifies into products that others already run better, because routing capital to them is more useful than competing with them.

**Nothing here has a date.** Each item ships when its dependencies are met, and each dependency is stated.

***

### Credit

#### 1. Credit Markets for Individuals

Score-gated, overcollateralized lending where your credit history discounts the collateral you post. Every other on-chain lender asks the same overcollateralization of a wallet that has repaid twenty loans as it does of a wallet created this morning. Synclear scores the borrower and prices them accordingly, so a proven record converts into capital efficiency.

Runs on Morpho Midnight, the first lending infrastructure supporting per-market verification and fixed-rate, fixed-term loans.

**Gated on:** Morpho Midnight reaching mainnet, and the individual scoring model proven in production. **Detail:** Credit Markets for Individuals

#### 2. Credit Markets for AI Agents

An AI agent never borrows on its own account. It borrows as an authorized instrument of a verified principal: a business that has passed KYB, or an individual who has been scored. The principal delegates a bounded mandate, and the agent operates inside it.

This matters because a single operator can create a thousand agents. Credit extended to an unverified agent is credit extended to nobody. Tying every agent to a verified principal, who remains liable for what the agent does within its mandate, is what makes agent borrowing safe rather than a Sybil attack with better branding.

**Gated on:** Morpho Midnight, agent mandate infrastructure, and the individual and business scoring models proven in production. **Detail:** Credit Markets for AI Agents

#### 3. Senior and Growth Credit Funds

Two ways to invest in the same originated loan book, rather than one.

The Senior Credit Fund takes first claim on repayments at a lower yield. The Growth Credit Fund is subordinate: it absorbs losses ahead of the senior tranche, and earns a higher return for doing so. The same underwriting, the same borrowers, and the same capture mechanism sit behind both.

The structure is standard in private credit, and it does something useful in both directions. Investors choose the risk they want rather than accepting one blended profile, and the junior tranche gives the senior one a genuine layer of protection that no marketing claim could substitute for.

**Gated on:** the credit book building a repayment record substantial enough to tranche honestly.

#### 4. Tokenized treasuries as borrower collateral

Businesses can post tokenized treasury bills as the collateral on their loan. The collateral keeps earning the treasury yield while it sits posted, which directly reduces the effective cost of borrowing.

Tokenized treasuries are the right collateral to start with because their value does not swing: they are backed by government debt, they are already accepted across on-chain lending at 70 to 80 percent loan-to-value, and the market has grown past $10 billion.

**Tokenized equities are deliberately excluded.** The infrastructure is not ready. A wrapped-stock exchange rate was manipulated in an exploit in July 2026 to inflate collateral roughly 78 times, and lending protocols listing tokenized equities have launched with borrowing paused entirely because liquidation behaviour and oracle design remain unproven. Liquidating a tokenized equity requires unwinding a wrapper and selling into a market that closes at night. Synclear will accept equity collateral when that is solved, and not before.

**Gated on:** oracle integration and collateral risk parameters.

#### 5. Order-book credit

Today, lending to Synclear's borrowers means investing in the Cashflow Credit Fund and holding a diversified book. Order-book credit lets a lender read the underwriting on a specific business and fund that loan directly, choosing exactly which borrowers they lend to.

It is a sharper and more robust instrument. A lender who funds a single loan holds that borrower's risk undiluted, where the fund spreads it across many. It is built for lenders who want that, and the pooled fund continues to backstop what the order book does not fill.

**Gated on:** enough lender depth that loans actually fill, and a track record that makes per-loan underwriting legible to those reading it.

***

### Platform

#### 1. Institutional mandates

Verified institutions get custom risk parameters, segregated exposure, and reporting, rather than pooling into products built for everyone. An institution with its own risk committee does not want a blended vault; it wants its own mandate, executed to its own constraints.

This is what asset managers do at scale, and it is where the infrastructure is heading: Coinbase routes billions through Morpho specifically because isolated vaults let institutions set their own parameters rather than pool with anonymous counterparties.

**Gated on:** traction, and institutional demand that justifies the operational cost of bespoke mandates.

#### 2. Multi-chain deployment

The vaults and markets deploy to additional chains as they mature. Synclear is built chain-agnostic; deployment follows liquidity and cost.

**Gated on:** liquidity depth and execution cost on each target chain.

***

### Governance

_SNC_ is Synclear's token, launching around mainnet. It is designed to do three things:

**Govern.** _SNC_ holders vote on protocol parameters: risk limits, fees, strategy approvals, and treasury allocation.

**Backstop.** Staked _SNC_ absorbs shortfalls, so stakers accept slashing risk in exchange for a share of protocol revenue. This makes the token part of the protocol's safety layer.

**Accrue value.** Protocol revenue funds _SNC_ buybacks, after the credit book's first-loss buffer and the protocol's insurance reserves are funded. Insurance and cover come first, always.

Synclear will remain CeDeFi in structure. Underwriting a borrower, holding assets with a custodian, and enforcing a defaulted loan all require a legal entity, and no vote can perform them. What decentralises is stewardship of the protocol's parameters, not the operation of its credit desk. Saying otherwise would be a decentralisation theatre that this protocol has no interest in performing.

**Full detail, including supply, distribution, and the revenue model, will be published in a separate tokenomics paper.** It is not summarised here.
