# Risk Disclosure

Every product on Synclear carries risk. This page sets out those risks in full. It is not a formality, and it is not written to be skimmed. Read it before depositing.

Nothing on this page or anywhere in this documentation is financial advice.

#### The risks that apply

1. **Smart-contract risk.** Synclear's contracts hold your funds. A vulnerability in them, or in the third-party protocols they deploy into, could result in the loss of some or all of your capital. Every contract is audited before it holds funds and covered by smart-contract insurance, but audits do not find every bug, and insurance pays after a loss rather than preventing it.
2. **Stablecoin risk.** Synclear holds and deploys third-party stablecoins. Each has its own issuer, its own backing, and its own peg risk. If a stablecoin Synclear holds loses its peg or its issuer fails, the value of the assets behind your position falls with it. This applies to every product, including Open Savings.
3. **Counterparty risk.** Your capital passes through custodians, executes on trading venues, and is deployed into third-party protocols and strategies. Each of these is a party whose failure, insolvency, or misconduct could cause a loss. Exposure is spread across multiple parties, which reduces the damage any one can do, but does not eliminate it.
4. **Oracle risk.** The protocol relies on price feeds. Redundant sources reduce the risk that a single feed misprices the system, but a coordinated or systemic oracle failure could still cause incorrect liquidations or valuations.
5. **Regulatory risk.** The regulatory treatment of on-chain lending, yield-bearing products, and synthetic assets is unsettled and varies by jurisdiction. Regulation could restrict, tax, or prohibit products you hold, or restrict your access to them.
6. **Access risk.** Verified products are subject to jurisdictional restrictions. Your eligibility can change if the rules of your jurisdiction change.

#### Open Savings

Open Savings holds tokenized treasury bills, on-chain overcollateralized lending positions, and liquid stablecoins. It takes no market or delta-neutral exposure and is the most conservative product Synclear offers. It is not risk-free.

1. **Issuer risk on tokenized treasuries.** Tokenized treasury bill products are issued by third parties. Their tokens depend on the issuer's solvency, custody, and redemption process, not only on the underlying government debt.
2. **Lending venue risk.** Capital supplied to on-chain lending markets is exposed to those markets: bad debt from an under-collateralized borrower, a failed liquidation, or an exploit of the lending protocol could cause a loss.
3. **Liquidity risk.** In extreme conditions, redeeming from underlying positions may not be immediate.

#### Managed Savings

Managed Savings carries every Open Savings risk, plus the following.

1. **Strategy risk, and you bear it.** The delta-neutral sleeve can lose money. Funding rates can turn negative, which reverses the yield of a funding strategy rather than merely reducing it. A hedge can slip, so a position intended to be market-neutral drifts and takes a directional loss. A venue can fail while positions are open.
2. **No reserve stands behind this account.** The strategy risk of the sleeve is borne by you. Chaser Insurance covers a technical failure of the algorithmic manager. It does not cover strategy losses, and a strategy losing money is not a technical failure.
3. **Manager risk.** Chaser allocates within protocol-defined limits it cannot exceed, but within those limits it makes decisions, and those decisions can be wrong. An allocation into a strategy whose yield then collapses is a normal outcome, not a malfunction.
4. **Third-party strategy risk.** Capital allocated to Ethena and Theo is exposed to those protocols in full: their custody, their venues, their hedges, and their solvency.

#### Options Yield Fund

1. **The value floats and can fall.** This is not a stable-value product. The share price reflects the strategy's performance, including its losses.
2. **Volatility risk.** The strategy is hedged against market direction, not against volatility. A sharp volatility spike can cause a significant loss.
3. **Defined-risk structures cap each position, not the book.** The maximum loss on any single position is bounded in advance. In a broad volatility event, many positions can move against the fund simultaneously, and the fund can draw down meaningfully even though no individual position exceeded its cap.
4. **No reserve and no first-loss buffer.** Market risk is held directly by the investor by design, and it is not insured.

#### Cashflow Credit Fund

1. **Credit risk.** You are a lender. Businesses fail, and some loans will not be repaid in full.
2. **Correlation risk, the tail worth naming.** The book is diversified across many borrowers, which protects it in normal conditions. In a broad downturn, many borrowers can weaken at once, and that diversification protects you least at exactly the moment it matters most.
3. **The buffer is not insurance, and it is finite.** Synclear's first-loss buffer absorbs losses on the loan book before they reach you, whatever the cause. It is Synclear's own capital, not a policy, and there is no claim to file. It is also sized against modelled losses, and a loss that exceeds it reduces the value of your investment directly. Beyond the buffer, credit risk is yours.
4. **Capture can fail.** Repayment depends on revenue continuing to arrive at addresses the protocol captures from. A borrower whose revenue collapses has nothing to capture. A borrower who diverts revenue to an address outside the agreement is in breach, and recovery then depends on enforcement against their verified legal identity, which is slower and less certain than capture.
5. **The loan book has no track record.** Synclear's credit book is new. The loss model behind it is built on external data and conservative assumptions, and until the book has been through a full cycle, its real loss rate is an estimate rather than a measurement.
6. **Liquidity.** The underlying assets are loans, not instantly liquid instruments. Redemption may be subject to available liquidity or a notice period.

#### For borrowers

1. **Capture reduces your working capital.** Between 5% and 18% of your revenue is routed to repayment as it arrives. Model your cash flow accordingly.
2. **Your terms can tighten.** If the health of your loan deteriorates, Synclear can raise your capture rate toward its maximum, freeze further draws, and accelerate the loan.
3. **Collateral can be liquidated.** Any collateral you post can be seized and sold against your balance if you default.
4. **Your loan is bound to your legal identity.** KYB means default is enforceable against your business through ordinary legal means, including debt collection.

#### Risk is bounded, not eliminated

Synclear's design contains risk in specific, structural ways. Products are ring-fenced from one another. Exposure is spread across venues and custodians. Every borrower is isolated, and none may exceed 5% of the credit fund. Losses run through a defined waterfall. Insurance covers Synclear's own failures.

None of this makes any product risk-free, and Synclear does not claim it does. Every one of these controls is bounded by the assumptions it was modelled on, and a sufficiently extreme event can exceed them.
