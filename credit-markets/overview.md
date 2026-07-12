# Overview

Synclear originates credit. It underwrites its own borrowers, prices its own loans, and collects on them, rather than assembling yield that someone else created. This is the part of the protocol that produces a return no other source in the market provides.

There are two credit markets, and they work differently because their borrowers are different.

#### Two borrowers, two models

* **Businesses borrow against their revenue, with little or no collateral.** A business earns from customers. That income arrives from outside the business, it is reasonably predictable, and it can be captured at the source. So Synclear underwrites the business on its live cash-flow data and routes an agreed share of each incoming payment to the loan as the revenue arrives. Repayment is mechanical rather than voluntary. Collateral is a lever, never a requirement above half the loan, and most borrowers post none.
* **Individuals borrow against collateral, discounted by their score.** An individual's income is self-generated rather than paid by customers. There is no incoming stream to sit in front of, so capture does not work, and lending to individuals against their trading performance is precisely the model that produced the largest losses in on-chain credit. Collateral does the work instead. But where every other lender demands the same overcollateralization from every anonymous wallet, Synclear scores the borrower and discounts it: a verified borrower with a strong on-chain record posts materially less collateral than a wallet with no history, for the same loan. The score converts into capital efficiency.

|                     | **Businesses**                         | **Individuals and AI agents**                 |
| ------------------- | -------------------------------------- | --------------------------------------------- |
| **Collateral**      | 0% to 50%, usually none                | Overcollateralized, discounted by score       |
| **Repayment**       | Automated capture of revenue at source | Repay or be liquidated                        |
| **Underwritten on** | Live cash-flow data (KYB)              | On-chain borrowing behaviour (four subscores) |
| **Recovery**        | Capture, collateral, legal enforcement | Liquidation of collateral                     |
| **Runs on**         | Synclear's native markets              | Morpho Midnight                               |
| **Status**          | Live                                   | Coming, see the Roadmap                       |

The business book is live and documented in this section. The individual and agent markets run on Morpho Midnight, whose per-market verification makes score-gated lending possible for the first time. Midnight is not yet live, so those markets are not available at launch. They are covered in the Roadmap.

#### Why on-chain credit has failed before

Two failure patterns account for most of the losses in this category, and both books are built to answer them.

**Unsecured lending to opaque borrowers.** The first generation of on-chain credit lent large sums to a handful of crypto trading firms on the strength of their reputation, with no way to monitor them and no mechanism to recover. When one concealed its exposure and failed, it took $36 million across eight loans, and the main pool lost most of its remaining capital because so much had been lent to that single borrower.

**Credit that cannot be enforced.** Other protocols lent to real-world businesses whose revenue lived off-chain, where repayment depended on the borrower choosing to pay and on collection systems the protocol could not reach. When borrowers stopped paying, there was little the protocol could do. Goldfinch wound down in 2026 after roughly $100 million originated, with depositors recovering a fraction of their principal.

Both share a root cause: **the lender had no mechanical claim on the borrower's money.** Repayment depended on willingness, and recovery depended on a courtroom.

#### How Synclear answers each failure

1. **Repayment is mechanical, not requested.** For businesses, an agreed share of each incoming payment is routed to the loan automatically as revenue arrives. For individuals, collateral is liquidated on-chain. In neither case does the protocol depend on a borrower choosing to pay, and in neither case does recovery depend on a lawsuit.
2. **We lend only where the claim is enforceable.** Businesses must have revenue that arrives on-chain and can be captured. Individuals must post collateral that can be liquidated. Synclear does not lend to off-chain businesses, however attractive the yield, because without a capturable stream the protocol is back to relying on a promise.
3. **Every borrower is underwritten on data, not reputation.** Businesses on live cash-flow history, individuals on their on-chain borrowing record. Underwriting sets the boundaries of the loan rather than issuing a verdict on the borrower.
4. **Every borrower is isolated.** Each loan sits in its own market, so a default is contained and cannot spread across the book. And no single borrower may hold more than 5% of the fund's deployed capital. The pool that was destroyed by one borrower had neither limit.
5. **There is a floor, and no price below it.** Businesses below a 670 credit score do not get a loan at a higher rate. They do not get a loan. Lending to weak borrowers at punitive rates is the merchant cash advance model, and it manufactures the defaults it prices for.

#### This is a loan, not a merchant cash advance

Revenue-based lending has a deserved bad reputation, and the business book uses a mechanism that looks superficially similar. The difference is worth being precise about.

Merchant cash advances carry effective rates of **40% to 150%**, hidden inside factor rates. They are sold through brokers who add a markup. They are stacked, so a business ends up with several advances capturing at once, and combined capture above roughly **20% of revenue** is what starves a business of working capital and causes the default. And they lend to almost anyone, at around a 500 credit score, because the pricing already assumes failure.

Synclear charges a stated APR of **15% to 35%** on the outstanding balance, so repaying faster costs less. Businesses come directly, with no broker in the price. Capture is capped at **18%**, below the level that suffocates a business, and because each borrower has one loan in one isolated market, stacking cannot happen unseen. And the 670 floor means Synclear lends to businesses that can repay rather than businesses that are desperate.

The capture mechanism is not what is wrong with merchant cash advances. Predatory pricing, hidden costs, broker markups, and lending to businesses that cannot afford it are what is wrong with them. Synclear uses the mechanism without any of them.

#### Who lends the money

Both books are funded by the Cashflow Credit Fund, whose investors are the lenders. Those investors knowingly carry the credit risk in exchange for the interest it earns. The savings accounts take no credit risk, and no depositor is exposed to lending they did not opt into.

#### What remains risky

Businesses fail, and some loans will not be repaid in full. Capture reduces the loss when a borrower weakens, because the protocol is already collecting as revenue arrives, and collateral, enforcement, and a first-loss buffer absorb what capture does not. None of this makes credit risk-free, and Synclear does not claim it does. What the design does is make repayment mechanical rather than voluntary, contain every failure to a single borrower, and ensure the losses that do occur fall on the investors who chose to carry them.

#### Explore the credit markets

[**Credit Markets for Businesses**](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/credit-markets/credit-markets-for-businesses) (live)

* How Borrowing Works, from verification and underwriting to the loan itself
* Collateral and Terms, what you can borrow, at what price, and how collateral improves it
* Repayment, Health, and Default, how capture works and what happens when a loan struggles

[**Credit Markets for Individuals**](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/protocol-roadmap/credit-markets-for-individuals) (coming)

* Covered in the Roadmap, including how a credit score discounts the collateral you post
