---
description: Coming with Morpho Midnight. Not available at launch.
---

# Credit Markets for Individuals

Every on-chain lender treats you like a stranger. Aave, Morpho, and Spark ask the same overcollateralization of a wallet that has repaid twenty loans as they do of a wallet created this morning, because on-chain lending has no memory. Your history earns you nothing.

Synclear scores you, and the score converts into capital efficiency. A verified borrower with a strong on-chain record posts materially less collateral for the same loan than an anonymous wallet does. You still post more collateral than you borrow, the loan is always overcollateralized and always liquidatable, but the gap between what you post and what you borrow narrows in proportion to what you have proven.

This is what a credit score is for, and DeFi has never had one.

#### Why individuals borrow against collateral, not revenue

Synclear's business book lends with little or no collateral, because a business earns from customers: that income arrives from outside, it is predictable, and it can be captured at the source as it lands.

An individual's income does not work that way. Trading profits are self-generated, not paid by a customer, so there is no incoming stream to sit in front of and capture. There is only a balance the borrower controls, and a balance can be moved to another wallet in seconds. Lending to individuals against their trading performance is not a new idea: it is the model that produced the largest losses in on-chain credit, when lenders extended undercollateralized loans to trading firms on the strength of their track records and lost tens of millions when those firms failed.

So collateral does the job that capture does for businesses. It makes the claim enforceable without depending on the borrower's cooperation, and liquidation is mechanical and immediate.

The score is what makes the loan yours rather than anonymous.

#### How the score changes your loan

Your score is built from your on-chain borrowing history and sets two things.

1. **How much collateral you post.** A strong score earns a higher loan-to-value, so you post less collateral for the same borrowed amount, and your capital works harder.
2. **What you pay.** Better-scored borrowers present less risk to the lender and are priced accordingly.

| --                     | Anonymous wallet, any protocol | Scored borrower, Synclear               |
| ---------------------- | ------------------------------ | --------------------------------------- |
| Collateral required    | The same as everyone else      | Discounted in proportion to your record |
| Rate                   | The same as everyone else      | Set by your score                       |
| Your repayment history | Counts for nothing             | Is the entire point                     |

#### What the score measures

Four sub-scores, all drawn from what you have actually done on-chain.

1. **Historical Harm.** What you have cost lenders before: liquidations, defaults, and bad debt, weighted by how recent and how severe they were. A clean record scores highest, and the first failures matter most.
2. **Risk Profile.** The risk appetite your behaviour reveals: how close to your limits you habitually borrow, how much leverage you carry, and how volatile the assets you post are. Measured over time, so a borrower cannot look conservative by being briefly conservative.
3. **Capital Solvency.** Your capacity to sustain a position: liquid reserves against outstanding debt, and total on-chain net worth against the size of what you are borrowing.
4. **Operator Quality.** Discipline, and the strongest single signal in the model: when a position of yours has deteriorated, did you act, topping up or repaying, or did you drift toward liquidation? Alongside how long you have been active, how diversified you are, and whether you use audited protocols.

Full detail is on [Your Credit Score](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/protocol-roadmap/credit-markets-for-individuals/your-credit-score).

#### Liquidation

An overcollateralized loan is protected by liquidation, and that protection is what allows the collateral discount to exist. Two measures govern it.

**Health Factor** is where you are now: the live ratio of your collateral to your debt. It is deterministic, and it is what triggers a liquidation.

**Liquidation Risk** is where you might be soon: a simulation of your collateral basket forward over days, returning the probability that you breach liquidation within that window. It does not liquidate you. It warns you, and it can restrict new borrowing while your position is fragile.

There is an honest trade in the collateral discount. A higher loan-to-value means your capital works harder and a smaller price move can liquidate you. The efficiency you earn is real, and so is the fragility that comes with it. See Liquidation and Risk.

#### Who can borrow

Verified individuals, and AI agents operating on-chain, in both cases with a wallet history substantial enough to score. A wallet with no record does not score well and does not earn a discount. It can still borrow at standard overcollateralization anywhere else in DeFi; what Synclear offers is the reward for a record, and a record has to exist first.

#### Why this runs on Morpho Midnight

Score-gated lending requires per-market control over who may borrow, and lending markets have not supported that. Morpho Midnight does: it allows markets with verification and address-level permissions, alongside fixed-rate, fixed-term loans. It is the first infrastructure on which a lending market can price a specific, verified borrower rather than an anonymous wallet.

Midnight is not yet live. These markets launch when it does, and when the individual scoring model has been proven in production.

#### In this section

* [How Borrowing Works](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/protocol-roadmap/credit-markets-for-individuals/how-borrowing-works), from verification to your loan
* [Your Credit Score](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/protocol-roadmap/credit-markets-for-individuals/your-credit-score), the four subscores and how to improve them
* [Liquidation and Risk](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/43/protocol-roadmap/credit-markets-for-individuals/liquidation-and-risk), Health Factor, Liquidation Risk, and the honest trade in a higher loan-to-value
