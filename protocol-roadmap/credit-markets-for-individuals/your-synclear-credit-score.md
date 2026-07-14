---
description: Coming with Morpho Midnight. Not available at launch.
---

# Your Synclear Credit Score

Your Synclear credit score runs from 300 to 850. It is built entirely from what you have done on-chain, and it determines how much collateral you post and what you pay.

Four subscores feed it. Each measures something a lender genuinely needs to know, and together they answer one question: if we ask you for less collateral than we ask a stranger, will that be a mistake?

#### 1. Historical Harm

**What you have cost lenders before.**

Every liquidation, default, and instance of bad debt in your history is recorded with a severity: a full liquidation counts fully, a partial liquidation counts in proportion, a close call that you recovered from counts lightly. Two things are then measured: how often these events happen relative to how much you have borrowed, and how deep the losses were when they did.

Both are weighted by recency. An event from last month weighs roughly two and a half times more than one from nine months ago, and the weight halves every six months. A liquidation in your past is not a permanent mark, but a recent one is a heavy one.

A clean record scores highest. The first failures cost the most, and further failures matter progressively less, because the signal is already sent.

#### 2. Risk Profile

**The risk appetite your behaviour reveals.**

Three things, all measured across your history rather than at a single moment, so that a borrower cannot appear conservative by being briefly conservative:

* **Utilization.** How close to your available limit you habitually borrow. A borrower who consistently uses the full loan-to-value available to them is telling the lender something.
* **Leverage.** The effective leverage you carry.
* **Collateral volatility.** How volatile the assets you post are. Posting blue-chip collateral is a different statement from posting long-tail tokens.

A more conservative revealed appetite scores higher. This is not a judgement about how you should invest; it is a measure of how much risk the lender is taking by extending you a discount.

#### 3. Capital Solvency

**Your capacity to survive a bad day.**

Two ratios:

1. **Reserves against debt.** Liquid assets you hold outside the position, relative to what you owe. This is what you would draw on to top up a position under stress.
2. **Net worth against position size.** Your total on-chain net worth relative to the size of what you are borrowing. A position that represents a small fraction of your capital is a different risk from one that represents most of it.

Both saturate. Going from one times coverage to two times matters a great deal; going from ten times to eleven barely matters at all, and the score reflects that.

#### 4. Operator Quality

**Your discipline, and the strongest signal in the model.**

**Responsiveness** is the heart of it and carries the most weight. When one of your positions has deteriorated toward liquidation, what did you do? A borrower who tops up or repays within a reasonable window is telling a lender exactly what it wants to know. A borrower who drifts toward liquidation and lets it happen is telling it the opposite. No other on-chain signal predicts repayment behaviour as directly.

Three further measures contribute:

1. **Tenure.** How long you have been active on-chain.
2. **Diversification.** Whether your capital is concentrated in one protocol or spread across several.
3. **Protocol safety.** Whether you operate through audited, established venues.

Involvement in exploits applies a severe penalty.

#### How the score is built

The four subscores are combined into a single number between 300 and 850. The same scale governs the business book, and the same thresholds mean the same things: 670 is the floor for a discount, and better scores earn progressively better terms.

**A wallet with too little history does not get the benefit of the doubt.** It scores low, and it earns no discount. It can still borrow at standard overcollateralization on any market in DeFi. What Synclear rewards is a record, and a record has to exist before it can be rewarded.

#### What is not in your score

* **Your current position.** How risky your open position is right now is not part of your creditworthiness. It is measured separately and continuously as Health Factor and Liquidation Risk, and it governs liquidation, not pricing. Mixing the two would mean that borrowing more made you look less creditworthy, which is circular and wrong.
* **Your identity beyond verification.** Synclear scores your on-chain behaviour. It does not import a credit bureau file, and your Synclear score has no relationship to a traditional credit score.
* **Your wealth alone.** Capital Solvency measures capacity, but a large balance does not buy a good score. A wealthy wallet that has been liquidated repeatedly scores poorly, and a modest wallet with a clean, disciplined record scores well. The score measures behaviour, and money is not behaviour.

#### Improving your score

1. **Do not get liquidated.** Historical Harm is the heaviest drag on a poor score, and the weight of past events decays over time.
2. **Act when your health falls.** Topping up or repaying under stress is the strongest positive signal available to you.
3. **Leave a buffer.** Habitually borrowing to your limit reveals an appetite that is priced for.
4. **Post and hold quality assets.**
5. **Build a history.** Tenure, diversification, and safe venues all contribute, and they only accrue with time.

Your score is a record of how you have behaved, so the only way to improve it is to behave differently, and then wait for it to show.
