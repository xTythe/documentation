---
description: Coming with Morpho Midnight. Not available at launch.
---

# Liquidation & Risk

Your loan is overcollateralized, which means it is protected by liquidation. If your collateral falls far enough relative to your debt, the position is closed and the collateral is sold to repay the loan.

That protection is what makes the collateral discount possible. Because the lender can always recover by liquidating, Synclear can afford to ask a proven borrower for less collateral than an unproven one. The discount and the liquidation are two sides of the same design.

Two measures govern your position, and they do different jobs.

#### Health Factor: where you are now

Your Health Factor is the live ratio of your collateral's value to your debt, adjusted for your loan-to-value. It is a present-tense fact, computed from prices as they are, with no assumptions in it.

**This is the number that liquidates you.** When it falls below the threshold, the position is liquidated. Nothing else triggers a liquidation, not your score, not a decision by Synclear, not a change of view about you as a borrower.

You raise your Health Factor by adding collateral or repaying debt. It falls when your collateral loses value or your debt grows with interest.

#### Liquidation Risk: where you might be soon

Your Health Factor tells you where you stand. It does not tell you how likely you are to be liquidated next week, and those are very different things. A position at the same Health Factor is far more dangerous when it is collateralized by a volatile, concentrated basket than by a stable, diversified one.

Liquidation Risk answers that. Synclear simulates your collateral basket forward over a horizon of days, running many paths using each asset's volatility and the correlations between your assets, and returns two numbers: the probability that your position breaches liquidation within the window, and how deep the loss tends to be on the paths where it does.

**Liquidation Risk does not liquidate you.** It does two things:

1. **It warns you.** You learn that your position is fragile while you still have time to act, rather than discovering it when the liquidation fires.
2. **It can restrict new borrowing.** While your Liquidation Risk is elevated, the protocol may prevent you from drawing more. This constrains new risk-taking, and it never reprices or accelerates the loan you already hold.

This is a measure almost no lending protocol provides, and it exists because Synclear is underwriting _you_, not just your collateral, and an underwriter that only knows where you stand today is not underwriting at all.

#### The honest trade in a higher loan-to-value

A better score earns you a higher loan-to-value. Your capital works harder: you borrow more against the same collateral, or post less collateral for the same loan.

**That same efficiency makes your position more fragile.** At a higher loan-to-value, a smaller fall in your collateral's price is enough to breach the liquidation threshold. The buffer between where you are and where you are liquidated is exactly the thing you have chosen to spend.

This is not a hidden cost, it is the product. Capital efficiency and liquidation buffer are the same quantity viewed from two directions, and a score allows you to convert one into the other. The right amount to convert depends on your collateral, your strategy, and your tolerance, and it is your decision.

Synclear's obligation is to make the trade legible, which is what Health Factor and Liquidation Risk are for. It is not to pretend the trade does not exist.

#### Avoiding liquidation

* **Watch Liquidation Risk, not just Health Factor.** A comfortable-looking Health Factor on a volatile, concentrated basket can breach quickly. Liquidation Risk is what tells you that.
* **Act early.** Topping up or repaying when your position deteriorates is both the thing that saves the position and the strongest positive signal in your score. The behaviour that protects you and the behaviour that improves your terms are the same behaviour.
* **Do not take the full loan-to-value simply because it is offered.** The discount is a ceiling, not a target.
* **Diversify your collateral.** Correlated collateral falls together, and Liquidation Risk accounts for exactly that.

#### If you are liquidated

The position is closed and your collateral is sold to repay the debt. The loss is contained: because the loan was overcollateralized, the lender is repaid, and what you lose is the collateral, not more.

A liquidation is recorded in your Historical Harm subscore, weighted by its severity and how recently it happened. It will reduce your score and your terms. Its weight halves roughly every six months, so it is a setback and not a permanent one, and it is the single most damaging thing you can do to your borrowing terms.
