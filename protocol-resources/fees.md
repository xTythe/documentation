# Fees

Synclear charges for the strategies it builds and the capital it manages. Where it routes your capital into someone else's strategy, it takes no share of that yield.

That principle produces the fee schedule below. Every fee is charged on yield or on assets under management, never deducted from your principal, and every one is published here rather than taken quietly as a spread.

#### 1. The schedule

| Product                  | Management fee | Performance fee                               |
| ------------------------ | -------------- | --------------------------------------------- |
| **Open Savings**         | None           | None                                          |
| **Managed Savings**      | 0.7%           | 10%, on Synclear-native strategy returns only |
| **Options Yield Fund**   | 0.7%           | 15%, above a high-water mark                  |
| **Cashflow Credit Fund** | 0.7%           | 15%, above the Open Savings rate              |
| **Borrowers**            | Interest only  | None                                          |

#### 2. Open Savings is free

Open Savings charges nothing. It holds tokenized treasury bills, on-chain lending, and cash, none of which Synclear created, so Synclear takes no cut of what they earn. The entire yield of the backing goes to the depositor.

This is a deliberate choice, not an introductory offer. Open Savings is the conservative front door to the protocol, and charging a fee to pass through it would be charging for someone else's work.

#### 3. Managed Savings: the Chaser fee, and a performance fee only on our own strategies

Two fees, and they pay for two different things.

**The 0.7% Chaser fee** is the management fee, charged on the whole account. Chaser is Synclear's algorithmic manager, and its work is allocation: deciding when to move capital toward the funding strategy because rates have spiked, when to pull back, and how to size everything within the protocol's risk limits. That work spans every strategy in the account, so the fee does too. You are paying for the manager.

**The 10% performance fee applies only to Synclear-native strategy returns.** When Chaser allocates your capital to Ethena's funding strategy, Theo's gold carry, tokenized treasury bills, or on-chain lending, Ethena, Theo, and those markets generated that yield. Synclear did not, and Synclear takes no share of it. The performance fee applies only to the return produced by Synclear's own options strategy.

In practice this means most of the yield in a Managed Savings account is never touched by a performance fee. A vault curator charging a flat 10% or 15% on all yield takes a materially larger share of the same return.

#### 4. The funds

**Options Yield Fund: 0.7% management, 15% performance above a high-water mark.** The strategy is Synclear's own, so the performance fee applies to all of its return. The high-water mark means that if the fund loses value, no performance fee is charged on the recovery until the previous peak is regained. You never pay twice for the same gain.

**Cashflow Credit Fund: 0.7% management, 15% performance above the Open Savings rate.** The hurdle matters. Synclear earns a performance fee only on the return the credit book generates _above what its own conservative, free savings account pays_. If the credit book does not beat Open Savings, there is no performance fee, because there was no reason to take the credit risk.

#### 5. Borrowers pay interest, and nothing else

Businesses borrowing from Synclear pay a stated APR on their outstanding balance. There are no origination fees, no application fees, no prepayment penalties, no maintenance fees, no broker commissions, and no legal costs passed back to the borrower. The rate you are quoted is the cost of the loan.

The cost of underwriting, verification, monitoring, and servicing a loan is carried inside that rate. It is paid by the borrowers who use the service, not deducted from the lenders who fund it.

#### 6. What Synclear does not do

**No hidden spread.** Some protocols pay savers a rate set by governance and quietly keep the difference between that rate and what the backing actually earns. The saver sees an APY and no fee, but the fee is the gap. Synclear publishes what it charges.

**No fee on yield it did not generate.** This is the principle the whole schedule rests on.

**No fee on principal.** Fees are charged on yield or on assets under management, and never come out of what you deposited.

#### 7. Where the fees go

Protocol revenue funds the operation of Synclear and capitalises the first-loss buffer that stands behind the Cashflow Credit Fund. The buffer is funded before the protocol takes profit.
