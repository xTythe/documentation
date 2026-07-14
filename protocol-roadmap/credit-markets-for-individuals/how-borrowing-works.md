---
description: Coming with Morpho Midnight. Not available at launch.
---

# How Borrowing Works

Borrowing as an individual takes four steps: verification, scoring, an offer priced to your score, and the loan itself.

#### Step 1: Verification

You verify your identity and connect the wallets you want scored. Verification is what allows a lending market to price you specifically rather than treat you as an anonymous address, and it is the reason a discount is possible at all.

Your score is built from your wallet history, so connecting the wallets where you have actually borrowed matters. A wallet with no borrowing record has nothing to score.

#### Step 2: Scoring

Synclear scores you from 300 to 850, on the same scale used for the business book, built from four measures of your on-chain borrowing behaviour:

| Subscore             | What it measures                                                                                                |
| -------------------- | --------------------------------------------------------------------------------------------------------------- |
| **Historical Harm**  | What you have cost lenders before: liquidations, defaults, and bad debt, weighted by recency and severity       |
| **Risk Profile**     | The risk appetite your behaviour reveals: habitual utilization, leverage, and the volatility of assets you post |
| **Capital Solvency** | Your capacity to sustain a position: liquid reserves against debt, and net worth against position size          |
| **Operator Quality** | Your discipline: above all, whether you act when a position deteriorates, or drift toward liquidation           |

A wallet without enough history to score does not receive a neutral benefit of the doubt. It scores low, and it earns no discount. Full detail is on [Your Synclear Credit Score](your-synclear-credit-score.md).

#### Step 3: Your offer

Your score sets two things.

1. **Your loan-to-value.** The higher your score, the more you can borrow against the same collateral. This is the whole product: the discount is proportional to the record you have built.

| Borrower                              | Typical loan-to-value                       |
| ------------------------------------- | ------------------------------------------- |
| Anonymous wallet on a standard market | The market's default, the same for everyone |
| Scored borrower on Synclear           | Higher, in proportion to your score         |

Every Synclear loan remains overcollateralized. The discount narrows the gap between what you post and what you borrow; it never closes it. Your loan is always liquidatable, which is what protects the lender and what makes the discount possible in the first place.

2. **Your rate.** Better-scored borrowers present less risk and are priced accordingly. Loans on Midnight are fixed-rate and fixed-term, so the cost is known when you take it.

#### Step 4: Borrow

You post collateral, borrow against it at your loan-to-value, and repay on the loan's terms. If your collateral falls far enough that your Health Factor breaches the liquidation threshold, the position is liquidated. Repay or top up before that happens, and nothing else occurs.

Two measures follow the loan for its life:

1. **Health Factor** is your live collateral-to-debt ratio. It is what liquidates you.
2. **Liquidation Risk** is a forward simulation of your collateral basket, returning the probability you breach liquidation over the coming days. It warns you before the Health Factor gets there, and it can restrict further borrowing while your position is fragile. It never liquidates you by itself.

See [Liquidation and Risk](liquidation-and-risk.md).

#### What improves your terms

Your score is not fixed. It responds to what you do.

* **Repay, and do not get liquidated.** Historical Harm dominates a poor score, and its weight decays with time. A liquidation matters most when it is recent.
* **Act when a position deteriorates.** Topping up or repaying when your health falls is the single strongest signal in the model. Drifting toward liquidation is the strongest negative one.
* **Borrow with a buffer.** Habitually borrowing to the edge of your limit reveals a risk appetite the score prices for.
* **Build a record.** Time, diversification across protocols, and the use of audited venues all contribute.

The intent is a lending relationship that compounds. Your fifth loan should cost less and demand less collateral than your first.
