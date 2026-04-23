---
layout:
  width: wide
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
---

# Credit Enhancement Vaults (CEV)

Credit Enhancement Vaults are the only module on Tythe that enables undercollateralized lending. LPs provide collateral backing to support TCT-verified borrowers on existing integrated lending markets. CEVs do not replace lending markets, they simply extend what those markets can offer.

The model is actuarial. Curators set the vault's risk parameters and borrower eligibility criteria. LPs provide the capital, bear the default risk, and earn Risk Premium share, float income, and TYT rewards in return.&#x20;

CEV owns every position it opens. The borrower interacts with CEV only, not with the lending market directly. CEV opens the position, holds the collateral claim, receives loan proceeds, and forwards them to the borrower's wallet. This ensures CEV can always reclaim its collateral contribution when a position closes.

***

<details>

<summary><strong>1. Curator Deploys</strong></summary>

Deployment is fully permissionless. No TYT stake required. Any CEP-verified individual or institution can deploy a CEV.

***

**Capital Structure**

**Total Fixed Deposit (TFD):** The vault's total capital capacity. The vault remains inactive and closed to borrowers until TFD is reached in full for the first time. Once activated, the vault is permanently active regardless of future LP withdrawals.

**Capacity Policy:** (_Immutable_)

* _Hard Close:_ Once the vault activates, it closes to new LP deposits. If existing LPs withdraw and total deposited capital drops below TFD, freed capacity reopens to new LPs on a first come first served basis.
* _Timelock Increase:_ Once TFD is reached, the curator may expand it via timelock. Expansion requires advance notice, giving LPs time to assess and exit before additional capital changes the vault's risk profile.

**LP Deposit Minimum (Optional):** The minimum deposit amount accepted from any single LP. Prevents dust deposits and sets a floor on LP commitment size.

**LP Deposit Maximum (Optional):** The maximum deposit amount accepted from any single LP. Caps concentration risk and ensures a distributed LP base.

**Risk Concentration Ratio (RCR):** (_Immutable_) Maximum active exposure as a percentage of TFD. An RCR of 70% on a $1M vault means no more than $700K can be committed in active positions at any time. New positions are blocked if committing them would breach the RCR.

***

**Collateral**

**Collateral Asset:** The asset the vault holds and deploys as collateral backing. AAA Class CAVB stablecoins exclusively at launch. AA Class CAVB assets (BTC, ETH, and LSTs) considered post-launch.

**Collateral Ratio:** (_Immutable_) The maximum vault contribution as a percentage of borrower collateral. The vault contribution is calculated as <mark style="color:blue;">`borrowerCollateral × Collateral Ratio`</mark>, capped at the borrower's MVV. A borrower posting $70,000 against a vault with a Collateral Ratio of 60% receives a $42,000 vault contribution, bringing their total collateral on the target lending market to $112,000.

***

**Borrower Eligibility**

**Vault Access Policy:** (_Immutable_)

* _Public:_ Any CEP-verified participant meeting the eligibility criteria is eligible on a first come first served basis.
* _Private:_ Curator defines a whitelist of eligible wallet addresses or CEP DIDs at deployment. Curator can update the whitelist via timelock post-deployment.

**TCT Score Minimum:** Minimum TCT score required for borrower eligibility. Required for Public vaults. Optional for Private vaults as an add-on filter.

**MVV Minimum (Optional):** Minimum MVV required for borrower eligibility. Filters out undercapitalized borrowers below a curator-defined threshold.

**MVV Maximum (Optional):** Maximum MVV permitted for borrower eligibility. Allows curators to scope their vault to a specific borrower capital profile and manage concentration risk.

***

**Fees**

**Risk Premium:** The percentage of each vault contribution paid by the borrower at position opening. Curator-defined within DAO-governed floor and ceiling bounds.

**Fixed Deployment Fee (Optional):** A one-time fee paid by LPs at entry. Compensates the curator for vault setup and ongoing management. Tythe retains 9% of every Fixed Deployment Fee collected when the fee switch is active.

</details>

<details>

<summary><strong>2. LP Deposits</strong></summary>

Any CEP-verified participant can deposit into a CEV as an LP. No minimum TCT required.

***

**Deposit Mechanics**

* LPs deposit the vault's exact collateral asset. No asset swaps permitted on entry.
* LP shares are minted at the current vault NAV. The first depositor receives shares equal to their net deposit amount. Subsequent depositors receive shares proportional to the current share price: <mark style="color:blue;">`shares = net deposit × total shares / total deposited`</mark>. Share price appreciates as Risk Premium income accrues and depreciates if a default occurs.
* Deposits are accepted on a first come first served basis until TFD is reached.
* No lock-up period. LPs can withdraw at any time subject to available vault liquidity above the RCR threshold.

***

**LP Yield**

Yield accrues via share price appreciation from three sources:

* **Risk Premium Share:** Proportional cut of Risk Premiums collected from borrower credit line openings. Tythe retains 9% of every Risk Premium collected when the fee switch is active. The remaining 91% is distributed to LPs according to share.
* **Float Income:** Investment yield generated by the curator deploying collected Risk Premiums into DAO-whitelisted AAA/AA yield strategies.
* **TYT Rewards:** Protocol-distributed TYT rewards for providing collateral backing to the credit layer.

***

**Curator Fee Structure**

* **Fixed Deployment Fee (Optional):** A one-time fee paid by LPs at entry. Tythe retains 9% when the fee switch is active. The remaining 91% flows to the curator.
* **Performance Fee (Float Income Only):** A percentage of float investment yield earned by the curator. Rate set at deployment within a DAO-governed ceiling.

Curators cannot take a fee on Risk Premiums. Risk Premiums reflect the actual risk taken by LPs and flow to the vault in full.

***

**Exit Mechanics**

* LPs can withdraw at any time subject to available vault liquidity. <mark style="color:blue;">`Available liquidity = total deposited — active credit line exposure`</mark>.
* No exit delay. Withdrawals execute immediately at the current share price.
* If available liquidity is insufficient to cover a withdrawal in full, the LP withdraws up to the available amount immediately. The remainder is queued and fulfilled as active credit line positions close and liquidity is restored.

</details>

<details>

<summary><strong>3. Borrower Access</strong></summary>

Any CEP-verified participant meeting the vault's eligibility criteria can open a position from an active CEV. CEV borrowers must complete traditional KYC in addition to the standard zk-KYC required elsewhere in the protocol. Traditional KYC is a CEV-specific requirement, giving curators and LPs an enforcement path in the event of default. All other protocol operations run on zk-KYC only.

***

**Eligibility Requirements**

**For Public vaults:**

* CEP verified
* Traditional KYC completed
* TCT at or above the vault's TCT Score Minimum
* MVV within the vault's MVV Minimum and Maximum bounds
* Vault has available capacity below the RCR threshold

**For Private vaults:**

* CEP verified
* Traditional KYC completed
* Wallet address or CEP DID on the curator's whitelist
* MVV within the vault's MVV Minimum and Maximum bounds
* Vault has available capacity below the RCR threshold

***

**How It Works**

The borrower interacts with the CEV contract via the Tythe Dashboard. CEV opens and holds every position on the borrower's behalf.

1. Borrower selects an eligible vault and specifies their collateral amount and target lending market
2. CEV calculates its contribution as <mark style="color:red;">`min(borrowerCollateral × Collateral Ratio, borrowerMVV)`</mark> and presents a full position summary for borrower review and confirmation: Target Lending Market, Total Posted Collateral, CEV Contribution, Borrower Contribution, Estimated Loan Amount, Risk Premium Due, and Repayment Obligations. The borrower confirms the exact terms before any funds move.
3. Borrower confirms, deposits their collateral into CEV, and pays the Risk Premium
4. CEV combines the borrower's collateral and its own contribution, opens the position on the target lending market under CEV's address, and receives the loan proceeds
5. CEV forwards loan proceeds directly to the borrower's wallet
6. Position is live. CEV holds the full collateral claim on the lending market for the duration of the position.

{% hint style="success" %}
TCT is verified at execution time, not request time. If TCT drops below the vault minimum between steps 1 and 5, the transaction is blocked.
{% endhint %}

{% hint style="info" %}
Borrowers may hold one active position per vault at a time.
{% endhint %}

</details>

<details>

<summary><strong>4. Position Lifecycle</strong></summary>

Once a position is opened, CEV holds the full collateral claim on the lending market until the position closes. No active monitoring is required for stablecoin positions. Collateral value is stable and LTV does not deteriorate through price movement.

***

**Repayment and Position Closure**

The borrower repays the loan directly to CEV. CEV forwards the repayment to the lending market and closes the position. The lending market releases the full collateral back to CEV. CEV returns the borrower's collateral share to their wallet and reclaims its contribution back into vault liquidity, freeing capacity for new positions within the RCR.

***

**Relay Emitter Signals**

All CEVs are auto-subscribed to Relay Emitter nEvent signals for their active borrowers. Curators and LPs receive real-time visibility into borrower credit events for the duration of every active position. These signals inform curator and LP decision-making but do not trigger automated vault actions on their own. Automated response to a Default nEvent is handled in Step 5.

***

**Post-Launch Note**

When AA Class CAVB assets are supported post-launch, active position health monitoring will become relevant as collateral values can fluctuate. Additional monitoring mechanics will be defined at that stage.

</details>

<details>

<summary><strong>5. Default Handling</strong></summary>

A default occurs when a borrower fails to repay their loan within the grace period defined by the target lending market. The Relay Emitter fires a Default nEvent for the borrower's CEP ID.

***

**Immediate Protocol Response**

When a Default nEvent is detected for an active CEV borrower:

* The borrower's TCT is slashed aggressively. CEV participation and subsequent default is treated as a severe credibility failure.
* The borrower's slashed TCT is reflected across all integrated markets.
* Repeat or severe defaults may result in protocol blacklisting.
* The borrower's access to all CEVs is suspended pending resolution.

{% hint style="danger" %}
**KYC disclosure on default.**&#x20;

Because CEV borrowers complete traditional KYC as a condition of access, the defaulting borrower's verified identity is surfaced to the affected vault's curator and LPs upon default confirmation. This gives curators and LPs the information needed to pursue legal enforcement outside the protocol if they choose to do so. Identity disclosure is accessible on default and limited to the affected vault's participants only.
{% endhint %}

***

**Loss Handling**

Since CEV holds the collateral claim on the lending market, the lending market's liquidation mechanism returns whatever collateral is recoverable to CEV directly. The borrower forfeits their collateral share on default allowing the CEV to retain all recoverable funds.

***

**No Protocol Backstop**

Tythe does not cover defaults. LPs opt into CEV yield and risk premiums with full knowledge that defaults are a possible outcome. The actuarial model depends on the curator selecting high-TCT and specified-MVV borrowers whose default rate remains below the vault's premium income rate.

</details>

<details>

<summary><strong>6. LP Exit</strong></summary>

LPs can exit a CEV at any time by withdrawing their deposited collateral asset in exchange for their vault shares.

***

**Withdrawal Mechanics**

* Withdrawals execute immediately at the current share price with no exit delay or lock-up period.
* <mark style="color:blue;">`Available liquidity = total deposited — active exposure`</mark>. Capital committed to active positions is not available for withdrawal until those positions close.
* If available liquidity is insufficient to cover a withdrawal in full, the LP withdraws up to the available amount immediately. The remainder is queued and fulfilled as active credit line positions close and liquidity is restored.

***

**Exit After a Default**

If a default has occurred and share price has depreciated, the LP exits at the current depreciated share price. No holding period applies. There is no delayed realization.

***

**Vault Capacity After Exit**

* Under Hard Close, LP withdrawals that bring total deposited capital below TFD reopen deposit capacity. New LPs can fill that capacity on a first come first served basis.
* Under Timelock Increase, LP withdrawals reduce available capital but do not affect the expanded TFD ceiling. New LPs can deposit up to the expanded ceiling.

</details>

<details>

<summary><strong>7. Sentinel Responsibilities</strong></summary>

The Sentinel is a safety role within the CEV. It has no control over funds and cannot initiate offensive actions. Its sole function is risk reduction. It can only act to decrease exposure, never to increase it.

***

**Sentinel Powers**

* **Float Deployment Oversight:** If the curator deploys Risk Premiums into a non-whitelisted strategy or a strategy that has deteriorated in risk classification, the Sentinel can immediately reverse the deployment and return capital to vault idle assets. No timelock required.
* **Risk Parameter Monitoring:** If a parameter change submitted by the curator via timelock would increase risk exposure, the Sentinel can revoke the pending action before it executes.
* **Emergency Deallocation:** If vault conditions deteriorate significantly, the Sentinel can deallocate float positions and return capital to vault idle assets immediately, without timelock, to preserve LP withdrawal capacity.

***

**What the Sentinel Cannot Do**

* Cannot move LP capital out of the vault
* Cannot close active borrower positions
* Cannot change vault parameters
* Cannot block LP withdrawals
* Cannot override the curator's borrower eligibility decisions

***

**Who Can Be a Sentinel**

The Sentinel role is assigned by the curator at deployment. A curator may assign a trusted third party, a risk management protocol, or retain the role themselves. The Sentinel address can be updated by the curator via timelock.

</details>

***

**Worked Examples**

***

Credit Line vaults turn existing collateral into maximum borrowing power. Top-Off vaults turn a credit need into a fully funded position. TCT scoring/whitelisting selects the borrowers. MVV defines the limits. The vault architecture distributes the risk across LPs who choose it.
