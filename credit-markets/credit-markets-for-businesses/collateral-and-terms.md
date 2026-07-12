# Collateral & Terms

Synclear lends against revenue, not collateral. Most borrowers post none. But collateral is available as a lever, and it is worth understanding, because it is the fastest way for a borrower to improve the terms of a loan.

#### Collateral is a dial, not a gate

Conventional on-chain lending is binary: post more than you borrow, or borrow nothing. Every loan on Aave, Morpho, or Maple is overcollateralized, which is safe for the lender but useless for a business that does not already hold more capital than it needs.

Synclear treats collateral as a continuous dial between 0% and 50%. Underwriting sets a minimum for each borrower, and the borrower may post more than that minimum to improve their terms.

**Your minimum is set by your risk profile.** Strong borrowers have a minimum of 0% and borrow against revenue alone. Weaker but eligible borrowers are given a positive minimum, the collateral that makes their loan acceptable in the first place.

**Anything above the minimum is your choice.** Posting more collateral than required improves your offer: a larger advance, a lower capture rate, a longer term, or a lower APR. Every borrower has this lever, whether their minimum is 0% or 40%.

**The minimum never exceeds 50%.** No Synclear loan is ever more than half covered by collateral, and none is ever overcollateralized. This is a deliberate limit. Past 50%, collateral starts doing the work that underwriting and capture are supposed to do, and the loan stops being a Synclear loan and becomes a commodity crypto loan available more cheaply elsewhere. If a business would need to post more than half the loan to be creditworthy, it is not a Synclear borrower.

<table><thead><tr><th width="155.1953125">--</th><th width="211.93359375">Aave/Morpho/Maple</th><th width="204.87890625">Merchant cash advance</th><th>Synclear</th></tr></thead><tbody><tr><td><strong>Collateral</strong></td><td>110% to 150%+</td><td>None</td><td>0% to 50%</td></tr><tr><td><strong>Underwriting</strong></td><td>None, collateral covers it</td><td>Minimal, price covers it</td><td>Live cash-flow data</td></tr><tr><td><strong>Who can borrow</strong></td><td>Anyone already holding crypto</td><td>Almost anyone, at a price</td><td>Businesses that can repay</td></tr></tbody></table>

#### What sets your terms

Four things determine what a borrower pays and how much they can take.

* **Your credit score,** from underwriting on live cash-flow data. It sets your tier, and your tier sets your advance ceiling and your rate band.
* **Your collateral,** at or above your minimum. More collateral means lower risk to the lender, and it is priced accordingly.
* **Your repayment history with Synclear.** Borrowers are scored continuously. Performance across credit cycles is the single biggest driver of improved terms over time.
* **Your choices within the offer.** A higher capture rate repays faster and shortens the term, which reduces the total interest paid. A lower capture rate preserves working capital but extends the loan and costs more overall.

#### Pricing

Rates are set by risk, and they are stated as a real annual percentage rate on the outstanding balance.

| Tier       | APR        |
| ---------- | ---------- |
| Superprime | 15% to 18% |
| Prime      | 18% to 25% |
| Standard   | 25% to 35% |

**Interest accrues on what you owe.** As the capture stream pays down principal, the balance falls and so does the interest. Repaying faster costs less. This sounds obvious, and it is how a loan is supposed to work, but it is not how this market prices.

Merchant cash advances are sold as a factor rate: borrow $100,000, repay $140,000, no matter when. The effective APR is 40% to 150%, and it is not disclosed. Flat-fee revenue-based lenders do the same thing more politely: a "6% fee" on a four-month advance is an effective 36% APR, and because the fee is fixed, a business that grows and repays early pays the same dollars over less time, making the effective rate worse. Growth is penalised.

Synclear's structure removes that. There is no factor rate, no flat fee, no early repayment penalty, and no broker commission built into the price. You are quoted a rate, and you pay interest on your balance.

#### Fees

Synclear charges interest. It does not charge origination fees, application fees, prepayment penalties, maintenance fees, or legal fees passed back to the borrower. The rate you are quoted is the cost of the loan.

#### Improving your terms

Terms improve in three ways.

1. **Post collateral above your minimum.** The most immediate lever, available at any time.
2. **Repay well.** Every completed credit cycle improves a borrower's score, and with it their advance ceiling, rate, term, and collateral requirement. A borrower's fifth loan should be materially cheaper than their first.
3. **Grow.** Advances are sized in months of revenue, so a business that grows its revenue raises its own ceiling.

#### Next

* [Repayment, Health, & Default](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/credit-markets/repayment-health-and-default), how capture works and what happens when a loan struggles
