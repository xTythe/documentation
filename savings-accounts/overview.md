# Savings Overview

Savings Accounts are the conservative core of Synclear. You deposit a stablecoin you already hold and earn a return on it while it stays a dollar. There are two accounts, Open Savings and Managed Savings. They share the same conservative DNA and differ in their objective: Open Savings protects your funds while earning a baseline return, and Managed Savings actively reaches for more yield within conservative limits.

#### The two accounts

Open Savings is the permissionless baseline. It is open to everyone with no verification and holds only conservative, dollar-stable positions: tokenized treasury bills, on-chain overcollateralized lending, and liquid stablecoins held as cash. It takes no market exposure and is designed to protect capital while earning a steady, near risk-free return. It is the simplest way to put idle dollars to work.

Managed Savings is the conservative way to chase yield. It holds the same base as Open Savings and adds a delta-neutral sleeve, then actively manages the whole mix. An algorithmic manager reallocates across the account's strategies within protocol-defined risk limits, moving toward whichever is paying best as conditions change. The posture stays conservative throughout, but the account works to earn more than a static mix would. Because it deploys into managed strategies and holds assets under institutional custody, it requires identity verification.

| --             | Open Savings                           | Managed Savings                                |
| -------------- | -------------------------------------- | ---------------------------------------------- |
| **Objective**  | Protect funds, earn a baseline return  | Actively reach for more yield within limits    |
| **Access**     | Everyone, no verification              | Verified users (KYC)                           |
| **Strategies** | Treasury bills, on-chain lending, cash | The same, plus delta-neutral strategies        |
| **Management** | Conservatively held                    | Actively reallocated by an algorithmic manager |

#### How the strategies work

Open Savings holds three conservative building blocks: tokenized treasury bills (such as BUIDL and USDY), on-chain overcollateralized lending (such as Aave and Morpho), and liquid stablecoins as cash. Each earns a dollar-denominated return that does not move with the crypto market.

Managed Savings holds those same three, plus a delta-neutral sleeve made up of Synclear's own hedged options strategy, Ethena's crypto funding strategy, and Theo's gold carry strategy. Delta-neutral means each position is hedged so it holds its dollar value regardless of market direction, which is what keeps the account conservative even as it reaches for more yield.

What makes Managed Savings distinct is that the allocation is not fixed. An algorithmic manager continuously shifts capital across these strategies within protocol-defined risk boundaries to capture the best available yield. If, for example, crypto funding rates spike and the funding strategy's return rises sharply, the manager can move more of the account toward it, then move back as conditions normalise. The result is a conservative portfolio that is actively worked, rather than a static one.

#### How savings work

Both accounts work the same way underneath. You deposit any allowlisted stablecoin, including

* USDC&#x20;
* USDT
* USD1
* USDe
* DAI/USDS
* USDG
* PYUSD
* RLUSD

and receive a savings token that represents your position. The token follows the ERC-4626 vault standard: its value grows as the account earns, so your balance compounds automatically with no action on your part. When you withdraw, you redeem the savings token for your share of the underlying assets, including the yield it has accrued.

Because the savings token is a standard vault share, it can be held, transferred, or used elsewhere while it continues to earn. The Open Savings token is permissionless and composes freely across open DeFi. The Managed Savings token is restricted to verified holders, in line with the account's access requirements.

#### Which account is for you

Open Savings is for anyone who wants to protect their stablecoins while earning a conservative return, with no verification and no lockup.

Managed Savings is for verified users who want to earn more without leaving the conservative design, and who prefer the allocation to be actively managed on their behalf rather than left static.

Full mechanics, backing detail, and the specific risks of each are on the [Open Savings](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/36/savings-accounts/open-savings) and [Managed Savings](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/36/savings-accounts/managed-savings) pages.

#### Risks

Both accounts are conservative, but neither is risk-free. Open Savings carries smart-contract risk, the counterparty risk of the venues and issuers it deploys into, and the risk of the stablecoins it holds. Managed Savings carries all of those plus the risk of its delta-neutral sleeve: funding can turn negative, hedges can slip, and a venue can fail. That risk is bounded by protocol-defined limits and covered by a protocol-owned reserve, but it is not eliminated. Each account's risks are detailed on its own page. Before depositing, please read the [Risk Disclosure](../protocol-resources/risk-disclosure.md) in full.
