# Mint SCD

Minting is how SCD enters circulation. You deposit USDC or USDT and receive SCD 1:1 in a single swap, open to anyone with no KYC and no whitelist. There is no queue and no approval step: the deposit and the SCD you receive settle in the same transaction.

{% hint style="info" %}
Minting SCD is always immediate and 1:1. Anyone, anywhere can mint, with no KYC and no counterparty approval. Earning yield and the gated products are the only actions that require verification, covered in their own sections.
{% endhint %}

This page covers what you can deposit, how a mint executes, and the fees involved. For what backs SCD and how it stays a dollar, see Synclear Dollar (SCD).

#### What you can deposit

SCD is minted only with:

* USDC
* USDT

You deposit either at a dollar of value and receive a dollar of SCD, 1:1. Blue-chip crypto and tokenized gold are not mint-allowlisted assets: they enter the protocol only as bounded strategy holdings, never as raw mint backing.

#### How a mint executes

You deposit USDC or USDT and receive SCD 1:1, immediately and in the same transaction. Because you are depositing a stablecoin, nothing needs hedging at mint, there is no execution cost or conversion, and no mint is refused or delayed under normal conditions.

What the protocol does with the backing afterward is a separate, ongoing decision. It never affects whether or when you can mint, and the overview is covered in [Synclear Dollar (SCD)](./).

**Per-block limits apply.** Minting is subject to a per-block cap on how much SCD can be issued in any single block. Under normal conditions you will never encounter this constraint. It is a standard safeguard that bounds issuance if anything goes wrong, and it is set and adjusted by governance.

#### Fees

* **Minting.** No protocol fee. USDC and USDT mint 1:1, with no execution cost and no slippage.
* **Redeeming.** No protocol fee in the normal case. Only redemptions that exceed the instant buffer and draw on slower backing carry a stress-only surge fee. See [Redeem SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/16/introduction/synclear-dollar-scd/redeem-scd).

#### After minting

SCD earns nothing while you hold it. To put it to work, save it into sSCD, covered in [Savings Accounts](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/16/savings-accounts). To exit back to a stablecoin, see [Redeem SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/16/introduction/synclear-dollar-scd/redeem-scd). For how the peg holds at a dollar throughout, see [Stabilize SCD](https://app.gitbook.com/o/0aiW3e41N69QHIAXxWlx/s/DJA9njN2uMlkeZuQfMaD/~/edit/~/changes/16/introduction/synclear-dollar-scd/stabilize-scd).
