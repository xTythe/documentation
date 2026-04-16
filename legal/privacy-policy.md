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

# Privacy Policy

### Tythe Protocol Privacy Policy

Last modified: April 15, 2026

This Privacy Policy (the "Policy") explains how Tythe Labs, Inc. ("Tythe," "the Company," "we," "us," or "our") collects, uses, and shares data in connection with the Tythe web application (app.tythe.network), [www.tythe.network](http://www.tythe.network/), and all of our other properties, products, and services (the "Services"). Your use of the Services is subject to this Policy as well as our Terms of Service.

***

#### High Level Summary

* Tythe Labs, Inc. is a Delaware C-Corp operating the Tythe Protocol and its associated Services.
* Tythe complies with applicable United States laws and regulations.
* The Tythe Protocol is a set of smart contracts deployed on the Base blockchain and other compatible networks. It is governed by Tythe DAO and is distinct from the Services operated by Tythe Labs, Inc.
* Tythe does not collect or store raw personal data such as your name, street address, date of birth, or IP address in connection with your use of the Services.
* Identity verification is handled entirely by Billions (ZKID Labs AG), a third-party zero-knowledge KYC provider. Tythe receives only a cryptographic attestation confirming verification status. Tythe never receives, stores, or processes your raw identity documents or personal information.
* Tythe collects publicly available on-chain data and limited technical data to operate and improve the Services.
* Credit Enhancement Profile (CEP) identifiers are anchored on the did:cheqd network. Tythe stores only the DID and associated on-chain resources — not the underlying personal information that generated them.
* Participation in the Credit Data Exchange (CDX) is entirely voluntary and consent-gated. Tythe does not access, compile, or share your credit data outside of active, participant-approved dataset orders.
* Any material changes to this Policy will be communicated via the Services.

***

#### Data We Collect

Privacy is foundational to the Tythe Protocol. The zero-knowledge architecture of the Services is designed to minimize data collection at every layer. We do not maintain user accounts in the traditional sense and do not collect or store raw personal data.

When you interact with the Services, we collect only:

**Publicly available blockchain data.** When you connect a non-custodial wallet to the Services, we collect and log your publicly available blockchain address to operate the Services and screen your wallet for prior illicit activity. Wallet addresses are publicly available data not created or assigned by us. Screening is conducted using intelligence provided by leading blockchain analytics providers.

**Zero-knowledge attestation data.** When you complete identity verification via Billions, Tythe receives a cryptographic attestation confirming that verification and sanctions screening have been completed. Tythe does not receive, process, or store your passport, biometric data, or any other personal information submitted to Billions. Your relationship with Billions is governed by Billions' own privacy policy and terms of service.

**Credit Enhancement Profile (CEP) data.** When you create a CEP, a did:cheqd decentralized identifier is minted and associated with your verified status and linked wallet addresses. Tythe stores this DID and its associated DID-Linked Resources — including wallet address mappings, TCT attestations, and verifiable credential statuses — as on-chain data. This data does not contain raw personal information.

**On-chain behavioral data.** To compute your Tokenized Creditworthiness (TCT) score, Tythe's scoring engine processes publicly available on-chain transaction history, DeFi position data, token balances, and other behavioral signals associated with your linked wallet addresses. This data is publicly available on the blockchain and is not created or assigned by us.

**Technical and device data.** We and our third-party service providers may collect limited technical data including browser type, device type, operating system, and referring pages to operate and improve the Services. We do not use this data to identify individual users.

**Communications.** We collect any information you provide directly to us via email, customer support, social media, or other support channels, including survey responses and feedback submissions.

**Employment applications.** If you apply for a position at Tythe Labs, we collect the information you provide through our application process including name, email, work history, and any other materials you submit.

***

#### Credit Data Exchange (CDX)

Participation in the CDX is entirely voluntary. No credit data is accessed, compiled, or shared without your explicit, order-specific consent.

When you opt into a CDX dataset order, Tythe compiles a Tythe Credit Report from your on-chain behavioral data and delivers it to the dataset buyer upon fulfillment of the minimum fill threshold. Your consent applies only to the specific dataset order you opt into. Opting into one dataset does not constitute consent for any other.

You may withdraw consent before your report is delivered. Withdrawn consent results in removal of your report from the dataset and forfeiture of the associated payout.

Tythe does not store, sell, or access your credit data outside of active, participant-approved dataset orders. Buyers receive a one-time report delivery. No ongoing data access is granted to buyers after delivery.

***

#### Relay Emitter

The Relay Emitter is an AI-powered intelligence layer that monitors publicly available on-chain behavioral patterns associated with CEP-linked wallet addresses. It classifies negative credit events (nEvents) and generates structured labels used internally for TCT scoring enforcement and externally for institutional subscriber feeds.

All data processed by the Relay Emitter is publicly available on-chain. No private or off-chain data is processed by the Relay Emitter without your explicit consent via zkTLS verification.

***

#### How We Use Data

We use the data we collect to:

* Operate, maintain, and improve the Services
* Compute and maintain TCT scores and MVV assessments
* Process and enforce on-chain credit events via the Relay Emitter
* Verify compliance status via zero-knowledge attestation
* Provide customer support and respond to inquiries
* Detect, investigate, and prevent fraudulent, unauthorized, or illegal activity
* Comply with applicable laws and regulations
* Generate aggregated, non-identifiable analytics to improve the Services

***

#### How We Share Data

We do not sell your personal information. We do not share your information with third parties for marketing purposes. We may share data only in the following circumstances:

**With service providers.** We may share limited data with trusted service providers who assist in operating the Services, including blockchain analytics providers, infrastructure providers, and the did:cheqd network. These providers are contractually bound to use data only for the purposes of providing their services to us.

**With Billions (ZKID Labs AG).** Identity verification is processed by Billions. Your interaction with Billions is governed by Billions' privacy policy. Tythe receives only a cryptographic attestation confirming verification status and does not receive or store any information submitted to Billions.

**With CDX dataset buyers.** Upon your explicit, order-specific consent, Tythe delivers your Tythe Credit Report to the dataset buyer. Delivery is a one-time transaction. No ongoing data sharing with buyers occurs after delivery.

**To comply with legal obligations.** We may disclose data as required by law, regulation, subpoena, court order, or government request. To the extent permitted by law, we will notify you of any such required disclosure.

**For safety and security.** We may share data to protect against, investigate, or stop fraudulent, unauthorized, or illegal activity affecting the Services, our users, or third parties.

**In connection with business transactions.** In the event of a merger, acquisition, bankruptcy, or other business transaction, data may be transferred to the relevant successor entity.

**With your consent.** We may share your information in any other circumstance where you have provided explicit consent.

***

#### Blockchain Data and On-Chain Limitations

You acknowledge that certain data associated with your CEP — including your TCT score, MVV, wallet addresses, and nEvent labels — is stored on public blockchains. This data is publicly visible and immutable by its nature. Tythe cannot edit, delete, or modify information stored on-chain, including your TCT balance, attestation records, and nEvent history. Requests to delete on-chain data cannot be fulfilled.

***

#### Third-Party Services

The Services may integrate with or contain links to third-party services, protocols, and platforms not operated or controlled by Tythe. Your use of those services is governed by their respective terms and privacy policies. Tythe is not responsible for the privacy practices of third-party services.

***

#### Security

We implement and maintain reasonable administrative, physical, and technical security safeguards to protect data from unauthorized access, disclosure, alteration, or destruction. Transmission over the internet is not completely secure and we cannot guarantee the security of data transmitted to or from the Services. You are responsible for the security of your wallet addresses, cryptographic keys, and CEP credentials.

***

#### Age Requirements

The Services are not directed at individuals under the age of 18. We do not knowingly collect personal information from minors. If you believe we have received information from a minor, please contact us at [privacy@tythe.network](mailto:privacy@tythe.network).

***

#### California Residents (CCPA)

We do not sell personal information as defined under the California Consumer Privacy Act (CCPA). California residents have the right to request information about data we have collected, request access to or deletion of that data, and to exercise these rights free from discrimination. To submit a request, contact us at [privacy@tythe.network](mailto:privacy@tythe.network). Note that we cannot fulfill requests to delete data stored on public blockchains.

***

#### European Union Data Subjects (GDPR)

We process personal data only to the extent necessary for the purposes described in this Policy. Our legal bases for processing include your consent, the performance of our Services, compliance with legal obligations, and our legitimate interests in operating and improving the Services.

Your rights under the GDPR include the right to access, rectify, restrict, or port your personal data, and to withdraw consent at any time. To exercise your rights, contact us at [privacy@tythe.network](mailto:privacy@tythe.network). Note that we cannot edit or delete information stored on public blockchains, including transaction data, wallet addresses, and on-chain attestations.

***

#### Changes to this Policy

We will notify you of any material changes to this Policy via the Services. Your continued use of the Services after changes are posted constitutes your acceptance of the updated Policy.

***

#### Contact Us

For questions about this Policy or how we collect, use, or share your information, contact us at:

[privacy@tythe.network](mailto:privacy@tythe.network)

Tythe Labs, Inc. \
1111b S Governors Ave STE 40937 \
Dover, DE 19904 \
United States
