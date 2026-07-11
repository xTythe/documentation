# Overview

Investment Funds are where Synclear steps beyond savings into higher-yield strategies. Where the savings accounts are designed to hold their value, the funds take defined strategy risk in exchange for higher potential return, and you hold that return and its risk directly. There are two funds at launch, the Options Yield Fund and the Cashflow Credit Fund, both available to verified users.

<figure><img src="../.gitbook/assets/Image 7-11-26 at 2.21 PM.png" alt=""><figcaption></figcaption></figure>

#### Funds versus savings

The difference between a fund and a savings account is where the risk sits.

A savings account is designed to hold its value. Your balance stays denominated in dollars and grows with the yield, and in Managed Savings a protocol-owned reserve stands behind the strategies.

A fund makes no such promise. Its share price floats with the performance of the strategy it runs, so it can rise faster than savings, and it can fall. There is no reserve behind a fund. When you invest, you hold the strategy's return and its risk directly. That is the trade: more potential yield, in exchange for taking the risk yourself.

Each fund is ring-fenced from the savings accounts and from the other fund, so its performance, good or bad, never reaches anything you did not opt into.

#### Available funds

1. **Options Yield Fund** runs Synclear's options book to harvest the volatility risk premium. It is the unbounded version of the options strategy that Managed Savings uses conservatively, run here to seek return rather than to protect a stable value.
2. **Cashflow Credit Fund** supplies the loans in Synclear's credit markets, so its investors are the lenders. It holds a diversified book of loans to on-chain businesses and earns the interest they pay.

| --             | Options Yield Fund                 | Cashflow Credit Fund             |
| -------------- | ---------------------------------- | -------------------------------- |
| **You are**    | An investor in an options strategy | A lender to on-chain businesses  |
| **Yield from** | The volatility risk premium        | Interest on business loans       |
| **Main risk**  | Market and volatility risk         | Credit risk across the loan book |
| **Access**     | Verified users                     | Verified users                   |

#### How the funds work

Both funds work the same way. You invest with a supported stablecoin and receive a fund share, an ERC-4626 token that represents your stake. The share price floats with the fund's net asset value: as the strategy earns, the share is worth more; if it loses, the share is worth less. You redeem the share for its current value, subject to the fund's liquidity terms.

Both funds are funded in stablecoins, ring-fenced from the rest of the protocol, and open to verified users only.

#### Which fund is for you

The Options Yield Fund is for verified users who want yield from a market-neutral options strategy run for return, and who accept that its value moves with the strategy's performance.

The Cashflow Credit Fund is for verified users who want to earn as a lender to real on-chain businesses, and who knowingly take the credit risk of that loan book in exchange for the interest it pays.

Full mechanics, strategy detail, and the specific risks of each are on the [Options Yield Fund](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/38/investment-funds/options-yield-fund) and [Cashflow Credit Fund](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/38/investment-funds/cashflow-credit-fund) pages.

#### Risks

The funds are higher-risk than the savings accounts by design. Each has a floating value that can fall, and neither has a reserve behind it: you hold the strategy's risk directly. Their specific risks, the market risk of the options strategy and the credit risk of the loan book, are detailed on their own pages. Before investing, please read the [Risk Disclosure](../protocol-resources/risk-disclosure.md) in full.
