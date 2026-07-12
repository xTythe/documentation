# How Borrowing Works

A business borrows from Synclear in four steps: verification, underwriting, an eligibility offer, and the loan itself. This page sets out each step, the criteria at every stage, and the numbers behind them.

#### Who can borrow

Synclear lends to businesses whose revenue arrives on-chain, because repayment is captured directly from that revenue as it arrives. Without a capturable on-chain revenue stream, the protocol would depend on a borrower choosing to pay, which is the failure that ended earlier on-chain credit protocols. This is a hard constraint, not a preference.

To qualify, a business must meet all of the following:

| Requirement      | Threshold                                            |
| ---------------- | ---------------------------------------------------- |
| On-chain revenue | Received on-chain and routable to a capture contract |
| Minimum revenue  | $10,000 per month                                    |
| Trading history  | At least 6 months                                    |
| Credit score     | 670 or above                                         |
| Verification     | KYB, direct with Synclear, no brokers                |

The 670 floor matters. Merchant cash advance providers routinely lend to businesses scoring 500 and below, then price for the defaults that follow. Synclear does not lend below the floor at any price. A business that cannot service a loan is not made a better borrower by being charged more.

#### Step 1: Verification (KYB)

The business verifies its legal identity, ownership, and control, and connects the on-chain addresses through which its revenue arrives. Businesses apply directly. There are no brokers in the process, and no broker markup in the price, which is one of the structural abuses of the merchant cash advance industry.

#### Step 2: Underwriting

Synclear underwrites on live cash-flow data, not on reputation or a pitch. The scoring engine reads the business's actual on-chain revenue history: how much it earns, how stable that income is, how it has trended, and how reliably it has met obligations.

The output is not a yes or no. It is a risk profile that sets the boundaries of the loan.

#### Step 3: Your eligibility offer

Underwriting returns an offer that defines what the business may borrow, expressed as five limits.

1. **Maximum advance.** Sized in months of revenue, and capped at launch by borrower tier:

| Tier       | Maximum advance        |
| ---------- | ---------------------- |
| Standard   | 0.75 months of revenue |
| Prime      | 1.25 months of revenue |
| Superprime | 1.8 months of revenue  |

These are conservative by design and in line with how the largest revenue-based lenders size advances against monthly revenue. They are also a starting point, not a ceiling. Borrowers who repay well across cycles earn larger advances and longer terms over time.

2. **Capture band, 5% to 18% of revenue.** The share of incoming revenue routed to repayment. The band has a hard ceiling for a specific reason: combined capture above roughly 20% of revenue is what starves a business of working capital, and it is the mechanism by which stacked merchant cash advances push businesses into default. Synclear's ceiling sits below that line, and because each borrower has a single loan in a single isolated market, capture cannot be stacked without the protocol seeing it.
3. **Term, up to 12 months.** Short-duration by design. Risk compounds over the life of a loan, so a short, self-liquidating loan is structurally safer than a long one, and 12 months is consistent with the payback windows used across revenue-based finance.
4. **Minimum collateral, 0% to 50%.** Strong borrowers post nothing and borrow against revenue alone. Weaker but eligible borrowers are given a minimum collateral requirement. It never exceeds 50%, so no Synclear loan is ever carried mainly by collateral. Underwriting and capture always do the work. Collateral is covered in full on the next page.
5. **Your rate: 15% to 35% APR, set by risk.** A stated annual rate on the outstanding balance, not a factor rate or a flat fee.

| Tier       | APR        |
| ---------- | ---------- |
| Superprime | 15% to 20% |
| Prime      | 20% to 26% |
| Standard   | 26% to 35% |

This is the part borrowers should compare most carefully. Merchant cash advances carry effective rates of 40% to 150%, concealed inside factor rates. Flat-fee revenue-based lenders advertise a "5% fee" that resolves to an effective 28% to 56% APR once repayment speed is accounted for, and because the fee is fixed, **repaying faster makes it more expensive**. A business that grows and clears its advance in four months can find a 6% fee has cost it 36% annualised.

Synclear charges interest on the outstanding balance. Repay faster and you pay less. There is no penalty for growing.

#### Step 4: Configure and draw

Within the offer, the business sets its own terms. It chooses the advance size up to its maximum, and the capture rate within its band. Those two choices determine the term, since the loan repays as revenue arrives, and the configuration must fit inside the 12-month cap. A business can post collateral above its minimum to improve any of these.

Once configured, an isolated market is created for that business alone, and the loan is funded by the Cashflow Credit Fundand disbursed in USDC or USDT, matched where possible to the currency the business earns in.

#### Isolation and concentration limits

Two structural limits protect the fund and, indirectly, the borrower.

**One borrower per market.** Each loan lives in its own isolated market. A default is contained to that market and cannot spread across the book. This is the direct answer to what happened to earlier on-chain lenders, where a single failed borrower could destroy most of a pool because so much had been lent into it.

**No borrower may take more than 5% of the fund's deployed capital.** Loan size is bounded not only by the business's own revenue but by the fund's total size, so no single borrower can put a meaningful share of lenders' capital at risk. At launch the book is deliberately small, and tickets scale up only as the book builds a repayment record.

#### Growing your terms

The initial offer is the floor, not the ceiling. Synclear scores borrowers continuously on their repayment behaviour, and a business that performs well across credit cycles earns better terms: a larger advance, a longer term, a lower rate, and a reduced or eliminated collateral requirement. A borrower who starts at 0.75 months of revenue can, over cycles, reach several months of revenue on materially better capital terms.

This is the intended path. Synclear is designed to lend to a business repeatedly, on improving terms, as it proves itself.

#### Next

* [Collateral & Terms](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/credit-markets/collateral-and-terms), the collateral model and how posting more improves your rate
* [Repayment, Health, & Default](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/credit-markets/repayment-health-and-default), how capture works and what happens if a loan struggles
