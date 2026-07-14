# Cashflow Credit Fund

The Cashflow Credit Fund is how you earn as a lender to real businesses. When you invest, your capital funds the loans that Synclear originates to on-chain businesses, and you earn the interest those businesses pay. It is the supply side of Synclear's credit markets: the businesses borrow, and the fund's investors are the lenders.

This is a differentiated source of yield. It is driven by the economics of real businesses rather than by crypto funding rates or market sentiment, so it does not rise and fall in step with the rest of the market.

#### What the fund holds

The fund holds a diversified book of loans to on-chain businesses. Each borrower passes KYB and is underwritten on live cash-flow data, and each loan is repaid through automated capture of the borrower's revenue at the source, rather than by relying on the borrower to send funds back. The full mechanics of underwriting, collateral, and capture are covered in the Credit Markets section.

The fund earns the interest on that book, and its share price reflects the book's performance. As loans are repaid with interest, the share gains value; if a loan is not fully recovered, the share reflects that loss.

#### What protects your capital

These loans are not fully collateralized, so protecting lender capital is central to the fund's design. When a loan runs into trouble, losses are absorbed in a fixed order before they can reach your investment:

First, the capture stream keeps paying down the loan from the borrower's ongoing revenue. Then any collateral the borrower has posted is seized and liquidated. Then Synclear's enforcement steps in, accelerating the loan, raising the capture rate to its maximum, and pursuing recovery against the borrower's verified legal identity. If a loss still remains, it is absorbed by the fund's first-loss buffer, a protocol-funded cushion built from retained revenue and seed capital, before any loss reaches investors. Only what exceeds the buffer falls to the fund and reduces its value.

Two further features contain risk. Every borrower sits in its own isolated market, so a single default is contained and cannot spread to the rest of the book. And the book is diversified across many borrowers, so no single loan determines the fund's outcome.

#### Insurance

The only form of insurance sits alongside the waterfall.

* **Smart-contract insurance**, provided by Chainproof and Nexus Mutual, covers losses from a technical failure or exploit of the fund's contracts.

#### First-loss cover

The first-loss buffer is Synclear's capital, funded from protocol revenue and seed capital, and it sits below you in the waterfall. Losses on the loan book hit it before they hit you, whatever caused them. There is no claim to file, no adjudication, and no argument about whether a default was our error or ordinary credit risk. If the book performs badly, Synclear's capital is destroyed first.

This is deliberate, and it is the strongest thing we can tell you about our underwriting. An originator that takes the first loss on its own book has every reason to underwrite it honestly. An originator that sells you the whole risk and keeps the fee does not.

Beyond the buffer, a soundly underwritten borrower who still defaults is the credit risk you knowingly took in exchange for the yield.

#### The honest risk

The fund's value can still fall. It carries real credit risk: businesses can fail, and not every loan will be fully recovered. The protections above reduce and contain losses; they do not remove them.

The tail risk worth naming is correlation. In a broad downturn, many borrowers can weaken at once, and the diversification that protects the book in normal conditions gives less protection exactly when it is needed most. The fund's first-loss buffer absorbs initial losses, but beyond it, ordinary credit losses reduce the fund's value directly. Its share price floats with the book's performance, and beyond the buffer and the insurance you hold the credit risk yourself, which is the reason the fund pays what it does.

At launch, the book is deliberately conservative: short loan terms, modest advances, high-quality borrowers, and small initial ticket sizes, scaled up only as the book builds a track record.

<figure><img src="../.gitbook/assets/Image 7-11-26 at 2.00 PM.png" alt=""><figcaption></figcaption></figure>

#### How to use the fund

{% stepper %}
{% step %}
#### **Invest**

Once verified, invest with a supported stablecoin. In return you receive a fund share, an ERC-4626 token representing your stake in the loan book.
{% endstep %}

{% step %}
#### **Earn**

The share's value floats with the fund's net asset value, rising as the book earns interest. There is nothing to claim; the return accrues in the share.
{% endstep %}

{% step %}
#### **Redeem**

Redeem the share for its current value, subject to the fund's liquidity terms. Because the underlying is a book of loans rather than instantly liquid assets, redemptions may be subject to available liquidity or a notice period.
{% endstep %}
{% endstepper %}

#### Access

The Cashflow Credit Fund requires identity verification (KYC) and is subject to the rules of each user's jurisdiction. Users are responsible for compliance with the laws that apply to them.

#### Risks

The fund carries credit risk: borrowers can default, and recovery may be partial. It carries correlation risk, since a broad downturn can weaken many borrowers at once. Its value floats and can fall. A first-loss buffer and insurance against Synclear's own failures sit in front of your capital, but they do not cover ordinary credit losses beyond the buffer, that risk is yours. The fund also carries the smart-contract and stablecoin risks common to the protocol. These risks are managed through underwriting, capture, collateral, isolated markets, diversification, the buffer, and insurance, but they are not eliminated. Before investing, please read the [Risk Disclosure](../protocol-resources/risk-disclosure.md) in full.
