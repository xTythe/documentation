# Repayment, Health, & Default

Repayment is the part of on-chain credit that has failed before, so it is the part Synclear has built most carefully. This page sets out how a loan repays, how its health is monitored, and what happens if it goes wrong.

#### Repayment happens automatically

A Synclear loan does not depend on the borrower deciding to pay. When the loan is created, a capture contract is placed on the addresses through which the business receives its revenue. From then on, an agreed share of each incoming payment, between 5% and 18%, is routed to the loan as the revenue arrives. The rest passes straight through to the business.

There is no invoice, no due date, and no monthly payment to miss. The loan repays as the business earns.

This is the single most important difference between Synclear and the on-chain credit protocols that failed. They lent money and then asked for it back. Synclear collects at the source, so repayment is mechanical rather than voluntary, and there is no gap between a business earning and its lender being paid.

#### Repayment moves with revenue

Because capture is a percentage rather than a fixed instalment, repayment scales with the business.

A strong month repays more. A slow month repays less. There is no fixed payment to default on when revenue dips, which is the failure mode of a conventional term loan, and there is no minimum weekly floor overriding the flexibility, which is a common piece of fine print in revenue-based advances that quietly reinstates fixed-payment pressure exactly when a business can least afford it.

Interest accrues on the outstanding balance, so a strong run of revenue that repays the loan early costs the borrower less. Growth is rewarded, not penalised.

#### Loan health is monitored continuously

Synclear scores every live loan in real time from the borrower's on-chain cash flow. The health factor reflects whether the loan is on track: whether revenue is holding up, whether capture is keeping pace with the schedule, and whether the business's underlying position is deteriorating.

Because the data is on-chain and continuous, problems surface early. A conventional lender learns a borrower is in trouble when a payment is missed. Synclear sees revenue softening as it happens, while the loan is still performing.

If health deteriorates, the borrower is contacted first. Most cash-flow problems are temporary, and a business that is still earning is still repaying. The protocol's interest is in the loan being repaid, not in accelerating a borrower who is going to recover.

#### If a loan struggles

Where health falls below defined thresholds, Synclear escalates in stages.

1. **Capture ratchets up.** The capture rate is raised toward its maximum, so more of each incoming payment goes to the loan. The loan repays faster from the revenue that still exists.
2. **Draws freeze.** No further capital is extended to the borrower.
3. **The loan accelerates.** The full outstanding balance becomes due.
4. **Collateral is seized.** Any collateral the borrower posted is liquidated against the balance.
5. **Recovery is pursued.** KYB binds the loan to a verified legal identity, so Synclear can pursue recovery through ordinary legal means, including debt collection. A borrower cannot walk away from an on-chain loan into anonymity.

#### The loss waterfall

If a loan is not fully recovered, the loss is absorbed in a fixed order. Each layer must be exhausted before the next is touched.

|   | Layer                 | What it does                                                                                  |
| - | --------------------- | --------------------------------------------------------------------------------------------- |
| 1 | **Capture stream**    | Continues collecting from whatever revenue the business still earns                           |
| 2 | **Posted collateral** | Seized and liquidated against the balance                                                     |
| 3 | **Enforcement**       | Acceleration, maximum capture, legal recovery against the verified borrower                   |
| 4 | **First-loss buffer** | A protocol-funded cushion, built from retained revenue and seed capital, absorbs what remains |
| 5 | **Fund investors**    | Only what survives all four layers reduces the value of the Cashflow Credit Fund              |

Two structural limits contain any single failure. Each borrower sits in an **isolated market**, so a default cannot spread to another loan. And no borrower may hold more than **5% of the fund's deployed capital**, so no single failure can take a meaningful share of lenders' capital. The protocol that lost most of a pool to one borrower did so because neither of these limits existed.

> **The first-loss buffer is Synclear's own capital.** It is not insurance, and there is no claim to file. Synclear's takes the hit before any investor is, whatever the cause of the loss. If the underwriting on this page is poor, Synclear pays for it first. That is the alignment behind every loan in the book.

#### What Synclear does not do

* **No confession of judgment.** Merchant cash advance contracts have historically required borrowers to sign away their right to contest a claim in advance, allowing the lender to seize assets without a hearing. Synclear requires no such waiver.
* **No blanket lien on your business.** Revenue-based lenders routinely file a UCC-1 lien against all of a business's assets, which blocks the business from obtaining other financing. Synclear takes a defined claim on a defined share of revenue, and posted collateral where applicable. Nothing else.
* **No stacking.** A business borrowing from Synclear has one loan in one isolated market with one known capture rate. The practice of layering multiple advances until combined capture suffocates a business cannot happen here.
* **No discretionary default.** A loan is in default when it meets defined, published conditions. There is no clause permitting Synclear to call the balance because it has formed a subjective view of the borrower.
* **No penalty for repaying early.** Interest is charged on the outstanding balance. Repay sooner and you pay less.

#### For lenders

Everything on this page is also a description of what protects the Cashflow Credit Fund. Capture means the fund is collecting continuously rather than waiting to be repaid. Continuous health scoring means deterioration is visible early. Isolation and the concentration cap mean no single borrower can damage the book. The waterfall means four layers absorb a loss before it reaches investor capital.

None of this eliminates credit risk. Businesses fail, and some loans will not be repaid in full. What the design does is make repayment mechanical rather than voluntary, surface trouble early, contain every failure, and ensure the losses that do occur fall on the investors who chose to carry them.
