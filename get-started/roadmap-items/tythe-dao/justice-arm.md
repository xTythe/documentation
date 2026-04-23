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

# Justice Arm

The Justice Arm of Tythe DAO handles disputed slashes and contested scoring events under the protocol's fixed launch formula. It is the mechanism through which participants can challenge enforcement decisions they believe were applied in error.

The Justice Arm is live at launch (V1.1). It operates independently of the Governance Arm and requires no token participation to access.

***

#### Raising a Dispute

To raise a dispute, a participant stakes a protocol-defined amount of TCT as a good faith deposit. This deposit serves two purposes: it filters out frivolous disputes and creates direct accountability for the participant's claim.

The stake is not a fee. Its fate depends entirely on the outcome of the case:

* If the Justice Arm rules the dispute is **overturned**, a portion of the staked TCT is burned.
* If the dispute is **sustained**, the full stake is returned to the participant.

Disputes must be raised within a protocol-defined window following the slash event. Disputes raised outside this window are not eligible for review.

***

#### How a Case is Heard

**Step 1: AI Clerk Preparation** \
When a dispute is submitted, an AI clerk automatically prepares an evidence brief from credit data associated with the CEP ID. The brief includes the full event record, the nEvent label assigned by the Relay Emitter, the percentile rank that determined slash severity, and all relevant transaction history. The clerk only prepares the brief, it does not deliver any verdict.

**Step 2: Jury Selection** \
A human jury is drawn from the pool of active Tythe participants whose TCT score falls within the same band as the disputant at the time of the slash. Disputes at band boundaries are heard by mixed juries drawn from both adjacent bands. Jury selection is randomized within the eligible pool.

**Step 3: Verdict** \
The jury reviews the AI clerk's brief and the on-chain record. They deliver a binary verdict: the dispute is overturned, or the dispute is sustained. The verdict is final. If sustained, the TCT balance is restored and the stake returned. If ruled against, the staked TCT is partially burned and the slash stands.

***

### Design Principles

* **Proximity-banded juries:** ensure that disputes are heard by participants with firsthand understanding of the credit behavior in question. A participant in the Poor bracket is not judged by participants in the Excellent bracket. Peers judge peers.
* **AI clerks prepare, humans decide:** The Relay Emitter classifies and the formula scores; but neither makes the final call on a contested dispute. Human judgment, informed by verifiable on-chain evidence, is the final layer of the system.
* **Frictionless settlement:** The dispute process is designed to be accessible to any participant with an on-chain history. The evidence brief is generated automatically. The process does not require legal representation or off-chain documentation.
