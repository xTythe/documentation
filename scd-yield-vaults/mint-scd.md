# Mint SCD

Minting is how _SCD_ enters circulation. You deposit an allowlisted asset and receive _SCD_ 1:1 in a single swap, open to anyone with no KYC and no whitelist. There is no queue and no approval step: the deposit and the _SCD_ you receive settle in the same transaction.

{% hint style="info" %}
Minting _SCD_ is always immediate and 1:1. Anyone, anywhere can mint, with no KYC and no counterparty approval. Only earning protocol yield by staking into _stSCD_ is subject to jurisdictional restrictions.
{% endhint %}

This page covers what you can deposit, how a mint executes, the fees involved, and how to redeem. For how the mechanism keeps _SCD_ fully backed and safe to scale, see [Synclear Dollar: SCD](../introduction/synclear-dollar-scd.md).

**What you can deposit**

_SCD_ can be minted from a basket of allowlisted assets across three categories. The allowlist is governed and expands over time.

* **Stablecoins.** USDC and USDT.
* **Blue-chip crypto.** ETH, WETH, wstETH, weETH, WBTC, and cbBTC.
* **Tokenized gold.** PAXG and XAUt.

Every deposit mints _SCD_ at a dollar of value for a dollar of asset, whatever the category. What differs is how the protocol conditions the backing behind it, described next.

**How a mint executes**

You receive _SCD_ 1:1, less the cost of executing any hedge or conversion. The protocol decides at the moment of minting how to handle the deposit, based on the asset and current market conditions:

1. **Deposit an allowlisted asset.** A stablecoin, blue-chip crypto, a liquid staking token, or tokenized gold.
2. **Stablecoin deposits issue immediately.** A dollar of stablecoin mints a dollar of _SCD_ on the spot. Nothing needs hedging.
3. **Volatile deposits are hedged when conditions are favorable.** The protocol opens a delta-neutral short of equal notional on a perpetual DEX in the same flow, then issues _SCD_. The short holds the dollar value of the backing steady as the asset's price moves, and its execution cost is priced into what you receive.
4. **Volatile deposits convert to stable when hedging is not favorable.** If funding is poor or the protocol's position limit across target venues is reached, the deposit is swapped to a liquid stablecoin instead, and _SCD_ is issued against that. No short is opened.
5. **Backing stays on-chain throughout.** Assets are held on-chain in protocol smart contracts. There is no centralized custodian and no exchange holding the backing.
6. **Per-block limits apply.** Minting is subject to a per-block cap on how much _SCD_ can be issued in any single block. Under normal conditions you will never encounter it; it exists as a standard safeguard that bounds issuance if anything goes wrong, and it is set and adjusted by governance.

The protocol makes this choice, not you, and it never delays your mint. Minting is always immediate and 1:1, and no deposit is refused. The hedge-or-convert decision governs what the backing becomes, never whether or when you can mint. The reasoning behind the convert path, and why it lets _SCD_ scale past the depth of any single venue, is covered in [Synclear Dollar: SCD](../introduction/synclear-dollar-scd.md).

**Fees**

* **USDC and USDT.** No protocol fee, in or out. These two swap 1:1 in both directions.
* **Blue-chip crypto and gold.** Minting carries a protocol fee plus the execution cost of opening the hedge or converting to a stablecoin, both priced into the _SCD_ you receive. There is no separate origination fee.
* **Redeeming beyond the instant buffer.** When redemptions exceed the instant USDC and USDT buffer and must draw on slower backing, they queue and a surge fee proportional to queue depth applies, paid to the _stSCD_ holders who remain.

**Redeeming SCD**

Redemption is the reverse swap: burn _SCD_ and reclaim a dollar of backing for each _SCD_. An instant USDC and USDT buffer held inside the mint and redeem engine serves redemptions immediately and at no fee, 1:1, up to its capacity. When redemptions exceed it, the remainder routes through the Withdrawal Queue as slower backing, such as open hedges, unwinds. How that buffer and continuous peg stability arbitrage hold _SCD_ at a dollar is covered in [Stabilize SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/12/scd-yield-vaults/stabilize-scd).

You can also exit _SCD_ without redeeming at all, by trading it on external AMM pools such as Uniswap, Aerodrome, or Curve against USDC, USDT, and other assets. Redeeming swaps with the protocol at par; trading sells on the open market at whatever price it is quoting.

> _SCD_ is a stablecoin and earns nothing while you hold it. To put it to work, stake into _stSCD_, covered in [Stake SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/12/scd-yield-vaults/stake-scd).
