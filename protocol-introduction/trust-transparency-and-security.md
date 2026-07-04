# Trust, Transparency & Security

When you deposit funds, you are trusting the protocol with your capital. Synclear is built so that trust rests on what you can verify, not on claims you take on faith. This page sets out how the backing is held, how the contracts are secured, where assets sit, how risk is managed, and how the credit book is underwritten.

#### Verifiable backing and transparency

Synclear's backing is held on-chain and can be inspected in real time. Rather than relying on periodic attestations of off-chain reserves, the assets behind every product sit in the protocol's own contracts and in vetted on-chain venues, where anyone can verify them directly. The transparency dashboard reports live backing, holdings, and strategy allocations across the protocol, so the state of the reserves is always open rather than disclosed on a schedule.

#### Security

Every Synclear contract is audited by independent security firms before it handles user funds, and the reports are published in the [Protocol Resources](https://app.gitbook.com/s/DJA9njN2uMlkeZuQfMaD/protocol-resources) section and on our Transparency Dashboard. The contracts are written to a conservative engineering standard that favours clarity and established patterns over complexity, since the smart-contract layer is the custody layer. Automated circuit breakers halt activity when predefined thresholds are breached, and price feeds draw on redundant oracle sources so that no single feed can misprice the system.

#### Custody and execution venues

Synclear runs its native hedged strategies across established derivatives venues: [Deribit](https://www.deribit.com), [Bullish](https://www.bullish.com), [Binance](https://www.binance.com/en), [OKX](https://www.okx.com), and [Bybit](https://www.bybit.com/en/). The backing that margins those positions is never deposited onto a trading venue. It is held off-exchange under institutional custody through off-exchange settlement (OES) with [Ceffu](https://www.ceffu.com), [Copper](https://copper.co/en), and [Fireblocks](https://www.fireblocks.com), and delegated to a venue only to margin a position, never transferred to it. If a venue were to fail, the backing remains with the custodian rather than on the exchange.

Where Synclear takes delta-neutral exposure, it allocates to established managers rather than rebuilding their strategies in-house: Ethena for crypto funding, and Theo for gold carry. Those positions are held as the managers' own tokens, acquired with stablecoins, so Synclear carries their strategy exposure without operating a trading desk of its own.

#### Risk management and design

Synclear does not run one pooled balance sheet at a single risk level. Each product has its own backing, its own risk profile, and its own return, and you choose which you hold. They are set out below from the most conservative to the most exposed. Each is ring-fenced from the others, so a loss in one cannot reach another, and reaching for higher yield is always your own decision.

**Savings Accounts:**

* **Open Savings** is the conservative floor. It holds only dollar-stable positions: tokenized treasury bills, on-chain money-market lending, and a small portion in liquid stablecoins held as cash. It is designed to hold its value while the backing earns, and it takes no market or delta-neutral exposure. The risks that remain are smart-contract risk, the counterparty risk of the lending venues and treasury-bill issuers it deploys into, and the risk of the stablecoins it holds. It is open to everyone with no verification.
* **Gated Savings** holds that same conservative base and adds a bounded delta-neutral sleeve, allocated to Ethena for crypto funding, Theo for gold carry, and Synclear's own hedged options positions. It is still designed to hold its value, but it carries the risk of that sleeve: funding can turn negative, hedges can slip, and a venue can fail. The exposure is capped by design, with the options component held to roughly 10 to 20 percent of notional, and a protocol-owned reserve is sized to absorb its modeled tail, so the added risk stays bounded rather than open-ended. Because it deploys into managed strategies and holds assets under off-exchange custody, it requires identity verification.

**Investment Funds:**

* **The Options Yield Fund** steps out of savings and into strategy risk. It runs Synclear's options book to harvest the volatility risk premium, and unlike the bounded sleeve inside Gated Savings, its exposure is not capped to protect a stable value. Its share price floats with the strategy's performance, and the investor holds both the return and the loss directly, with no reserve behind it. The strategy uses defined-risk structures that cap the loss on any single position, but that loss can still be meaningful in a sharp move. It is for verified users who choose to take that risk.
* **The Cashflow Credit Fund** is the supply side of the credit markets, and its investors are the lenders. It holds a diversified book of loans to on-chain businesses, and its share price floats with how that book performs. When a borrower defaults, losses absorb in a fixed order before reaching the fund: the capture stream, then the borrower's posted collateral, then enforcement against their verified identity, and only the uncovered remainder falls to the fund's value. The honest tail is correlation: in a broad crypto downturn many borrowers weaken at once, and the diversification that protects the book in normal conditions erodes exactly when it is most needed. It is for verified users who knowingly carry credit risk.

Across all of these, the controls are structural. Products are ring-fenced from one another. Strategies run across multiple venues and custodians, so no single point of failure can halt the protocol or endanger backing. Circuit breakers and redundant price oracles bound the damage from extreme events. Together these controls contain risk within modeled limits. They cannot eliminate it entirely, which is why we ask every user to read the [Risk Disclosure](../protocol-resources/risk-disclosure.md) in full before depositing.

#### Underwriting integrity

The credit markets lend to on-chain businesses, and the discipline behind that lending is part of the protocol's risk posture. Every borrower passes KYB and is underwritten on live cash-flow data before a loan is approved. Repayment runs through automated revenue capture at the source of the borrower's income, rather than depending on a promise to pay. Each loan sits in its own isolated market, so one borrower's default is contained and cannot spread to another. Losses absorb in a fixed order: the capture stream first, then any collateral the borrower has posted, then enforcement against the borrower's verified legal identity, and only then the fund's lenders. The book is funded by the Cashflow Credit Fund, whose investors knowingly carry that risk; it never touches the savings accounts for conservative profile savers.

#### Legal and compliance

Synclear is operated by a registered Delaware C-corporation. Access reflects a compliance-oriented design: depositing into Open Savings is open to everyone with no verification, while the gated savings tier, the investment funds, and borrowing require identity verification (KYC for individuals, KYB for businesses) and are subject to the rules of each user's jurisdiction. Users are responsible for compliance with the laws that apply to them.

For the underlying evidence, audit reports, disclosures, oracle specifications, and the live transparency dashboard, see [Protocol Resources](https://app.gitbook.com/s/DJA9njN2uMlkeZuQfMaD/protocol-resources). Before depositing into any product, please read the Risk Disclosure in full.
