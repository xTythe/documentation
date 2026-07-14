# Trust, Transparency & Security

When you deposit funds, you are trusting the protocol with your capital. Synclear is built so that trust rests on what you can verify, not on claims you take on faith. This page sets out how the backing is held, how the contracts are secured, where assets sit, how risk is managed, and how the credit book is underwritten.

#### Verifiable backing and transparency

Synclear's backing is held on-chain and can be inspected in real time. Rather than relying on periodic attestations of off-chain reserves, the assets behind every product sit in the protocol's own contracts and in vetted on-chain venues, where anyone can verify them directly. The transparency dashboard reports live backing, holdings, and strategy allocations across the protocol, so the state of the reserves is always open rather than disclosed on a schedule.

#### Security

Every Synclear contract is audited by independent security firms before it handles user funds, and the reports are published in Protocol Resources. The contracts are written to a conservative engineering standard that favours clarity and established patterns over complexity, since the smart-contract layer is the custody layer. Automated circuit breakers halt activity when predefined thresholds are breached, and price feeds draw on redundant oracle sources so that no single feed can misprice the system.

#### Custody and execution venues

Synclear runs its hedged strategies across established derivatives venues: [Deribit](https://www.deribit.com), [Bullish](https://www.bullish.com), [Binance](https://www.binance.com/en), [OKX](https://www.okx.com), and [Bybit](https://www.bybit.com/en/). The backing that margins those positions is never deposited onto a trading venue. It is held off-exchange under institutional custody through off-exchange settlement (OES) with [Ceffu](https://www.ceffu.com), [Copper](https://copper.co/en), and [Fireblocks](https://www.fireblocks.com), and delegated to a venue only to margin a position, never transferred to it. If a venue were to fail, the backing remains with the custodian rather than on the exchange.

Where Synclear takes delta-neutral exposure, it allocates to established managers rather than rebuilding their strategies in-house: [Ethena](https://ethena.fi) for crypto funding, and [Theo](https://theo.xyz) for gold carry. Those positions are held as the managers' own tokens, acquired with stablecoins, so Synclear carries their strategy exposure without operating a trading desk of its own.

#### Risk management and design

Synclear does not run one pooled balance sheet at a single risk level. Each product has its own backing, its own risk profile, and its own return, and you choose which you hold. They are set out below from the most conservative to the most exposed. Each is ring-fenced from the others, so a loss in one cannot reach another, and reaching for higher yield is always your own decision.

**SAVINGS ACCOUNTS**

* **Open Savings Account** is the conservative floor. It holds only dollar-stable, peg-stable positions: tokenized treasury bills, on-chain money-market lending, and liquid stablecoins held as cash. It is designed to hold its value while the backing earns, and it takes no market or delta-neutral exposure. The risks that remain are smart-contract risk, the counterparty risk of the lending venues and treasury-bill issuers it deploys into, and the risk of the stablecoins it holds. It is open to everyone with no verification.
* **Managed Savings Account** holds the same conservative base and actively reaches for more yield across it. An algorithmic manager, Chaser, shifts capital across the account's strategies within protocol-defined risk limits: the treasury bills, on-chain lending, and cash of Open Savings, plus a delta-neutral sleeve allocated to Synclear's hedged options, Ethena for crypto funding, and Theo for gold carry. As conditions change, it moves toward whichever strategy is paying best, so the mix is managed rather than fixed. The posture stays conservative by design: the sleeve is delta-neutral, the Synclear options strategy runs at a conservative exposure of roughly 10 to 20 percent rather than the unbounded level used in the Options Yield Fund, and the whole allocation sits within limits the manager cannot exceed. It is designed to hold its value, but it carries the risk of the sleeve, funding can turn negative, hedges can slip, a venue can fail, and that strategy risk is borne by the investor rather than a reserve. Chaser Insurance covers a technical failure of the manager, not strategy losses. Because it deploys into managed strategies and holds assets under off-exchange custody, it requires identity verification.

**INVESTMENT FUNDS**

* **The Options Yield Fund** steps out of savings and into strategy risk. It runs Synclear's options book to harvest the volatility risk premium, and unlike the conservative options exposure inside Managed Savings, it is not held down to protect a stable value. Its share price floats with the strategy's performance, and the investor holds both the return and the loss directly, with no reserve behind it. The strategy uses defined-risk structures that cap the loss on any single position, but that loss can still be meaningful in a sharp move. It is for verified users who choose to take that risk.
* **The Cashflow Credit Fund** is the supply side of the credit markets, and its investors are the lenders. It holds a diversified book of loans to on-chain businesses, and its share price floats with how that book performs. When a borrower defaults, losses absorb in a fixed order before reaching the fund: the capture stream, then the borrower's posted collateral, then enforcement against their verified identity, then the fund's first-loss buffer, and only the remainder beyond that reduces the fund's value. The honest tail is correlation: in a broad crypto downturn many borrowers weaken at once, and the diversification that protects the book in normal conditions erodes exactly when it is most needed. It is for verified users who knowingly carry credit risk.

Across all of these, the controls are structural. Products are ring-fenced from one another. Strategies run across multiple venues and custodians, so no single point of failure can halt the protocol or endanger backing. Circuit breakers and redundant price oracles bound the damage from extreme events. Together these controls contain risk within modeled limits. They cannot eliminate it entirely, which is why we ask every user to read the Risk Disclosure in full before depositing.

#### Insurance and cover

Synclear insures its own failures, and where insurance is the wrong instrument, it puts its own capital at risk instead. A contract exploit or a manager malfunction is insured. A loss on the credit book is absorbed by Synclear's own money before it reaches an investor. And where a loss is simply the market outcome of a strategy an investor knowingly chose, it is neither insured nor absorbed, because it is the risk they were paid to take.

* **Smart-contract insurance.** Every product that holds capital is covered against a technical failure or exploit of its contracts, provided by [Chainproof](https://www.chainproof.co), a regulated, institutionally-focused underwriter, alongside [Nexus Mutual](https://nexusmutual.io). Claims are adjudicated by independent technical investigation rather than by a vote.
* **Chaser Insurance, on Managed Savings.** Managed Savings is run by Chaser, Synclear's algorithmic manager. Chaser Insurance reimburses investors for a loss caused by a technical failure of the manager itself. It does not cover strategy losses: a delta-neutral position that loses money to negative funding or a slipped hedge is risk the investor took, not an operational failure.
* **Retained first loss, on the Cashflow Credit Fund.** Synclear does not insure its credit book. It stands behind it with its own capital. A first-loss buffer, funded from Synclear's revenue and seed capital, absorbs losses on the loan book before any loss reaches an investor, whatever the cause of the loss. If Synclear underwrites badly, Synclear pays for it first, and there is no claim to file and no argument about whose fault it was. Beyond the buffer, ordinary credit losses reduce the fund's value: a soundly underwritten borrower who still defaults is the credit risk the investor knowingly took.

Open Savings and the Options Yield Fund carry smart-contract insurance only. Open Savings holds conservative assets that need no further cover, and the Options Yield Fund is a floating-NAV strategy whose risk the investor takes directly by design. The providers and policies are listed in Protocol Resources.

#### Underwriting integrity

The credit markets lend to on-chain businesses, and the discipline behind that lending is part of the protocol's risk posture. Every borrower passes KYB and is underwritten on live cash-flow data before a loan is approved. Repayment runs through automated revenue capture at the source of the borrower's income, rather than depending on a promise to pay. Each loan sits in its own isolated market, so one borrower's default is contained and cannot spread to another. Losses absorb in a fixed order: the capture stream first, then any collateral the borrower has posted, then enforcement against the borrower's verified legal identity, then the fund's first-loss buffer, and only then the fund's lenders. The book is funded by the Cashflow Credit Fund, whose investors knowingly carry that risk; it never touches the savings accounts or the conservative backing.

#### Legal and compliance

Synclear is operated by a registered Delaware C-corporation. Access reflects a compliance-oriented design: depositing into Open Savings is open to everyone with no verification, while the Managed Savings tier, the investment funds, and borrowing require identity verification (KYC for individuals, KYB for businesses) and are subject to the rules of each user's jurisdiction. Users are responsible for compliance with the laws that apply to them.

For the underlying evidence, audit reports, disclosures, oracle specifications, and the live transparency dashboard, see Protocol Resources. Before depositing into any product, please read the [Risk Disclosure](../protocol-resources/risk-disclosure.md) in full.
