# Providers

Synclear does not operate in isolation. Your capital passes through custodians, executes on trading venues, is deployed into third-party strategies, and is insured by external underwriters. Every counterparty that touches it is listed here.

#### 1. Custody

Backing that margins Synclear's hedged positions is never deposited onto a trading venue. It is held off-exchange under institutional custody and delegated to a venue only to margin a position, never transferred to it. If a venue fails, the backing remains with the custodian.

| Custodian      | Role                                                |
| -------------- | --------------------------------------------------- |
| **Ceffu**      | Off-exchange settlement                             |
| **Copper**     | Off-exchange settlement                             |
| **Fireblocks** | Off-exchange settlement and transfer infrastructure |

Multiple custodians are used deliberately. No single custodian failure can halt the protocol or strand its backing.

#### 2. Execution venues

Synclear's hedged options strategies execute on established derivatives venues.

| Venue       |
| ----------- |
| **Deribit** |
| **Bullish** |
| **Binance** |
| **OKX**     |
| **Bybit**   |

Exposure is spread across venues rather than concentrated, so no single venue is a point of failure.

#### 3. Strategy allocations

Where a strategy is already run well elsewhere, Synclear allocates to it rather than rebuilding it. These positions are held as the managers' own tokens, acquired with stablecoins.

| Manager    | Strategy                      |
| ---------- | ----------------------------- |
| **Ethena** | Crypto funding, delta-neutral |
| **Theo**   | Gold carry, delta-neutral     |

Synclear charges no performance fee on the returns these strategies generate. See Fees.

#### 4. Yield venues

Open Savings and the conservative base of Managed Savings deploy into the following.

| Venue               | Exposure                            |
| ------------------- | ----------------------------------- |
| **BlackRock BUIDL** | Tokenized US treasury bills         |
| **Ondo USDY**       | Tokenized US treasury bills         |
| **Aave**            | On-chain overcollateralized lending |
| **Morpho**          | On-chain overcollateralized lending |

#### 5. Insurance

| Provider                    | Cover                                                                                                                                                                     |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chainproof**              | Smart-contract failure and exploit. A regulated, institutionally-focused underwriter, with claims adjudicated by independent technical investigation rather than by vote. |
| **Nexus Mutual**            | Smart-contract failure and exploit.                                                                                                                                       |
| **Third-party underwriter** | Underwriting error on the Cashflow Credit Fund, adjudicated independently.                                                                                                |

Chaser Insurance, covering technical failure of the algorithmic manager on Managed Savings, is funded by protocol revenue with third-party underwriting where additional capacity is required. Details are on Trust, Transparency & Security.

#### 6. Deposit assets

Synclear accepts the following stablecoins.

| Asset     |
| --------- |
| **USDC**  |
| **USDT**  |
| **USDe**  |
| **USDS**  |
| **USD1**  |
| **PYUSD** |
| **RLUSD** |

Loans are disbursed in USDC or USDT, matched where possible to the currency the borrower earns in.

#### 7. Infrastructure

| Provider            | Role                                                                               |
| ------------------- | ---------------------------------------------------------------------------------- |
| **Morpho**          | Isolated market infrastructure for the credit book                                 |
| **Morpho Midnight** | Fixed-rate, permissioned markets for score-gated individual lending. Not yet live. |

#### 8. Why these counterparties

Each is chosen for one of three reasons: it is the best operator of a strategy Synclear has no edge in, it is infrastructure Synclear would gain nothing by rebuilding, or it is a custodian or insurer whose independence is the point.

Counterparty risk is real, and it does not disappear because a counterparty is reputable. Every venue, custodian, and manager on this page is a party whose failure could affect Synclear. That is why exposure is spread across several of each, and why the risks are set out in full in the Risk Disclosure.
