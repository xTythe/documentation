# Managed Savings Account

Managed Savings is the conservative way to chase yield. It holds the same conservative base as Open Savings and adds a delta-neutral sleeve, then actively manages the whole mix to earn more than a static portfolio would, while keeping a conservative posture throughout. It is available to verified users.

Where Open Savings is built to protect capital while earning a baseline return, Managed Savings is built to reach for the best available yield within conservative limits. Same dollar-stable DNA, a different objective.

#### What Managed Savings holds

Managed Savings deploys across two groups of strategies.

**The conservative base**, the same three building blocks as Open Savings: tokenized treasury bills (such as BUIDL and USDY), on-chain overcollateralized lending (such as Aave and Morpho), and liquid stablecoins held as cash.

**The delta-neutral sleeve**, three hedged strategies that earn yield without taking directional market risk:

* **Synclear Options (volatility).** Synclear's own options strategy, harvesting the volatility risk premium. In Managed Savings it runs at a conservative exposure, not the unbounded version offered separately in the Options Yield Fund.
* **Ethena (crypto funding).** Yield from the funding paid on perpetual futures, captured through a delta-neutral position and accessed by allocating to Ethena rather than rebuilding the strategy.
* **Theo (gold carry).** Yield from the gold carry trade, accessed through Theo.

Delta-neutral means each position is hedged so that it holds its dollar value regardless of which way the market moves. This is what lets the sleeve add yield while keeping the account conservative.

#### How Managed Savings is managed

The distinguishing feature of Managed Savings is that its allocation is not fixed. An algorithmic manager continuously allocates across the account's strategies within protocol-defined risk boundaries, moving capital toward whichever is paying best as conditions change.

For example, if crypto funding rates spike and the Ethena funding strategy's yield rises sharply, the manager can increase the account's allocation to it, then reduce it again as funding normalises. If lending demand rises, it can lean further into on-chain lending. The account is a conservative portfolio that is actively worked, rather than a static mix left to sit.

The risk boundaries are set by the protocol, not by the manager. Within them, the manager optimises for yield; it cannot move the account outside the conservative limits that define it.

#### Why it stays conservative

Reaching for more yield does not mean taking open-ended risk. The account stays conservative by design in several ways. Its base is the same dollar-stable holdings as Open Savings. Its sleeve is delta-neutral, so the volatile positions are hedged and hold their dollar value regardless of market direction. The Synclear options strategy runs here at a conservative exposure, deliberately held well below the unbounded level used in the Options Yield Fund. And the whole allocation sits within protocol-defined risk limits that the manager cannot exceed.

The account is still designed to hold its value, and it carries more risk than Open Savings. The strategy risk of the sleeve is borne by you: in a tail event, such as deeply negative funding or a failed hedge, the account can lose value. That is the risk you accept in exchange for the higher yield.

#### Chaser Insurance

Managed Savings is run by Chaser, Synclear's algorithmic manager. Chaser Insurance protects you against a technical failure of Chaser itself: if the manager malfunctions and causes a loss through a technical fault, rather than through a strategy simply losing money, investors are reimbursed.

It does not cover strategy losses. The sleeve losing value because funding turned negative or a hedge slipped is strategy risk you knowingly took, and it is not insured. Chaser Insurance covers Synclear's operational failure, not the market outcomes you opted into. Smart-contract insurance, provided by Chainproof and Nexus Mutual, additionally covers losses from a technical failure or exploit of the account's contracts.

#### How to use Managed Savings

{% stepper %}
{% step %}
#### **Deposit**

Once verified, deposit any supported stablecoin, including USDC, USDT, USDe, and USDS. In return you receive the Managed Savings token, an ERC-4626 vault share that represents your position.
{% endstep %}

{% step %}
#### **Earn**

The token's value grows as the account earns, so your balance compounds automatically. There is nothing to claim or restake, and nothing to manage yourself: the allocation is handled for you.
{% endstep %}

{% step %}
#### **Withdraw**

Redeem the Managed Savings token for your share of the underlying, including accrued yield.
{% endstep %}
{% endstepper %}

The Managed Savings token follows the ERC-4626 standard, but unlike the Open Savings token it is restricted to verified holders, in line with the account's access requirements.

#### Access

Managed Savings requires identity verification (KYC). Verification is required because the account deploys into managed strategies and holds assets under off-exchange institutional custody, and because access is subject to the rules of each user's jurisdiction. Users are responsible for compliance with the laws that apply to them.

#### Risks

Managed Savings carries every risk that Open Savings does, smart-contract risk, the counterparty risk of the venues and issuers it uses, and the risk of the stablecoins it holds, plus the risks of its delta-neutral sleeve. Funding rates can turn negative, reducing or reversing the yield on the funding strategy. Hedges can slip, so a position intended to be delta-neutral can drift and take a loss. And an execution or custody venue can fail. These sleeve risks are bounded by protocol-defined limits, but they are borne by you: no reserve absorbs them. Chaser Insurance covers a technical failure of the manager, and smart-contract insurance covers an exploit of the contracts, but neither covers ordinary strategy losses. Before depositing, please read the [Risk Disclosure](../protocol-resources/risk-disclosure.md) in full.
