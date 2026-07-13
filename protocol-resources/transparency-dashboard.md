# Transparency Dashboard

Synclear's backing is held on-chain and can be inspected in real time. The dashboard reports what the protocol holds, where it is deployed, and how it is performing, as it happens rather than on a reporting schedule.

**Open the dashboard**

#### What the dashboard shows

* **Backing and holdings.** Total assets under management, broken down by product and by strategy. What is in tokenized treasury bills, what is in on-chain lending, what is held as cash, and what is deployed into each delta-neutral strategy.
* **Allocation, live.** The current allocation of Managed Savings across its strategies, and how Chaser has moved it. Allocation is not a static number in this account, and the dashboard shows where it stands now.
* **Yield, by source.** What each strategy is earning, so a depositor can see not only their rate but where it comes from.
* **The credit book.** Total loans outstanding, the number of active borrowers, the distribution of loan sizes, repayment performance, and the size of the first-loss buffer. Individual borrower identities are not published, but the book's performance is.
* **Custody and venue exposure.** How much backing sits with each custodian and how much is margining positions on each venue.
* **Insurance.** Active cover and its limits.

#### Why this matters

Most yield products ask you to trust a periodic attestation. A reserve is audited quarterly, a report is published, and between reports you take the issuer's word for it.

Synclear's holdings are on-chain, which means they can be verified continuously by anyone, including by people who do not trust Synclear. That is a stronger property than a good attestation, and it is the reason the protocol keeps its backing on-chain wherever it can.

Where backing is held off-exchange with a custodian in order to margin a hedge, it cannot be read directly from a block explorer. Those balances are attested by the custodians and reported here.

#### What the dashboard does not show

* **Borrower identities.** Businesses that borrow from Synclear are verified through KYB, and their identities are held by the protocol, not published. The book's performance is public; its borrowers are not.
* **Positions that would be exploitable if published in real time.** Live options positions are reported with a delay where publishing them immediately would allow the protocol's own book to be traded against, at the direct expense of the depositors in it. The delay is disclosed, and the positions are published in full once that risk has passed.

This is the one place where Synclear withholds information, and it does so because publishing it immediately would harm the people whose money it is. Everything else is live.
