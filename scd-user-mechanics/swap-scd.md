# Swap SCD

Minting is how _SCD_ enters circulation. You deposit USDC or USDT and receive _SCD_ 1:1 in a single swap, open to anyone with no KYC and no whitelist. There is no queue and no approval step: the deposit and the _SCD_ you receive settle in the same transaction.

{% hint style="info" %}
Minting _SCD_ is always immediate and 1:1. Anyone, anywhere can mint, with no KYC and no counterparty approval. Only earning protocol yield by staking into _stSCD_ is subject to jurisdictional restrictions.
{% endhint %}

This page covers what you can deposit, how a mint executes, the fees involved, and how to redeem. For how the mechanism keeps _SCD_ fully backed and safe to scale, see [Synclear Dollar: SCD](../introduction/synclear-dollar-scd.md).

#### What you can deposit

_SCD_ is minted with USDC or USDT only. You deposit either at a dollar of value and receive a dollar of _SCD_, 1:1. Blue-chip crypto and tokenized gold are not mint allowlisted assets. They are used elsewhere in the protocol, as Credit Markets collateral and as funding for delta-neutral hedge slots.

#### How a mint executes

You deposit USDC or USDT and receive _SCD_ 1:1, immediately and in the same transaction. Because you are depositing a stablecoin, nothing needs hedging at mint, there is no execution cost or conversion, and no mint is ever refused or delayed.

What the protocol does with that backing afterward is a separate, ongoing decision, not part of your mint. It routes stable backing into delta-neutral hedges where funding and venue capacity allow, and holds the rest in liquid stablecoin yield strategies. That choice governs what the backing becomes, never whether or when you can mint.

Backing stays on-chain throughout, held in the protocol's own contracts or in its own accounts on decentralized perpetual venues. There is no centralized custodian and no centralized exchange holding the backing.

Per-block limits apply. Minting is subject to a per-block cap on how much _SCD_ can be issued in any single block. Under normal conditions you will never encounter it; it exists as a standard safeguard that bounds issuance if anything goes wrong, and it is set and adjusted by governance.

The reasoning behind the hedge-or-hold decision, and why it lets _SCD_ scale past the depth of any single venue, is covered in [Synclear Dollar: SCD](../introduction/synclear-dollar-scd.md).

#### Fees

* Minting and redeeming. No protocol fee, in or out. USDC and USDT swap 1:1 in both directions.
* **Redeeming beyond the instant buffer.** When redemptions exceed the instant USDC and USDT buffer and must draw on slower backing, they queue and a surge fee proportional to queue depth applies, paid to the _stSCD_ holders who remain. This is a stress-only mechanism, not a standing fee.

#### Redeeming SCD

Redemption is the reverse swap: burn _SCD_ and reclaim a dollar of backing for each _SCD_. An instant USDC and USDT buffer held inside the mint and redeem engine serves redemptions immediately and at no fee, 1:1, up to its capacity. When redemptions exceed it, the remainder routes through the Withdrawal Queue as slower backing, such as open hedges, unwinds. How that buffer and continuous peg stability arbitrage hold _SCD_ at a dollar is covered in [Stabilize SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/12/scd-yield-vaults/stabilize-scd).

You can also exit _SCD_ without redeeming at all, by trading it on external AMM pools such as Uniswap, Aerodrome, or Curve against USDC, USDT, and other assets. Redeeming swaps with the protocol at par; trading sells on the open market at whatever price it is quoting.

> _SCD_ is a stablecoin and earns nothing while you hold it. To put it to work, stake 1:1 for _stSCD_, covered in [Stake SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/12/scd-yield-vaults/stake-scd).
