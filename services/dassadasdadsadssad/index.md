---

copyright:

  years:  2017

lastupdated: "2017-09-25"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with Ylabs
{: #gettingstarted}

The Ylabs Marketplace is complete banking stack, with APIs for compliant account opening flows, provision to add payees, and money transfer via several channels, with real time risk monitoring capabilities. KYC flows are built in by default into account opening flows, as well as available satnd-alone. KYC service calls five endpoints for OFAC, IDV, phone, email and IP verification.

{: #shortdesc}

<!-- If overview content is required, do not include it here. Put it in a separate "## About" section below the task section. -->

<!-- Task section: REQUIRED
The task section includes steps to integrate the service into the app.  
- With task-based, technical information, reduce the conversational style in favor of succinct and direct instructions.
- DO include the basic, most-common-use scenario steps to use the service or integrate it into the app. 
- DO NOT include steps to add the service from the Bluemix catalog; we assume that the user already took steps in the UI to add the service. 
- DO include code snippets in all languages that can be copied, as well as VCAP service info.  
- For additional tasks like configuring, managing, etc., add a task section (## Gerund_task_title) below the task section or "About" section if used. Use a task title such as "Configuring x", "Administering y", "Managing z". -->

<!-- You can include an optional prerequisites paragraph for any prerequisites to be met before integrating the service. For example: -->

1. Before an application developer can access the Ylabs APIs, they need to submit a product request. A product is an assembly of features, wrapped under the security and compliance layer. 
2. Once the product request is submitted, the product needs to be approved at the backend. It is typically done within a few minutes, after which the developer receives an email notification on the email address registered during product request. The email gives instructions on how to log in to the developer portal and also the unique token that the developer will need to use to run the API via the sandbox explorer.
3. In order to access the APIs externally (outside the developer portal) and to integrate them with their front end, the developer will have to supply one or more static IP addresses for white-listing. 
4. Ylabs provides free 1000 trial credits. If the developer would like to continue their subscription, they will need to upgrade to a paid account. Account upgrade information is provided in the instruction email.
5. The headers to be used, while sending API requests, are also provided in the instructions.
6. Once the developer logs into the developer portal, there are different resources such as 'Docs', 'Guides' and 'Explorer'. The 'Docs' section contains API documentation, 'Guides' contains a reference product implementation, beginner's guide and version management, and 'Explorer' is the place where a developer can send sample API requests to the sandbox and receive responses, while logged into the developer portal.

## About

This section gives a brief overview of the different categories of APIs available in Ylabs. Each category described below has 1-10 APIs. The request for every API goes through our real-time risk management system which risk scores every financial and non-financial transaction. Every entity in the system is tokenized, including accounts, payees and payment channels.

### 1. Enhanced KYC:
YLabs offers the KYC service in two ways: baked-in with the account creation process or as a standalone service. 
YLabs Enhanced KYC service connects to five services internally and returns an aggregated response about OFAC, IDV, IP, mobile number and email address that will help you to make an educated decision about the risk associated with a customer. The IDV service also has an in-built support for Out of Wallet (OOW).

### 2. Account Creation 
There is a set of APIs for account creation - consumer cardless, business cardless and consumer with cards. You can get a cardless account to begin with, and add physical and/or virtual cards at a later stage, via the add card APIs.
Consumer account creation calls consumer KYC internally, business account creation calls business KYC. This is a basic bank account created with a $0.00 balance. The The consumer and business accounts have an account number and routing number which makes them externally addressable and allows the account holder to perform credit and debit transactions through several payment channels.

### 3. Funding Source:
This set of APIs allows the account holder to link an external funding source, validate it, and make it available for credits and debits to and from the account.

### 4. Add payee:
After the account holder has successfully linked an external funding source and funded the account, they would need to add payees to their account in order to send money. There are APIs available to add consumer as well as business payees. You can also add international payees.

### 5. Add payment channels:
There are several ways in which money can be moved in to or out of the account, called payment channels. Money can be moved in to the account, either by a Deposit transaction or third party generated credit, which are both ACH processes. These are enabled via the linked external funding source and the externally addressable account / routing numbers. Wire is also an option to move money in. 
Our APIs support ACH, Instant payment via ATM rails, internal transfers, international remittance and wires for sending money out. 
We also support a payee directed model, where the sender does not have the burden of knowing the payees' payment channels. Instead the sender just needs to know the email address of the recipient and the amount to be sent, and the recipient can enter their payment channel details on their own.
For international remittance, there are several channels, such as Currency Cloud, Transfer-to or sending money to India via a correspondent bank relationship.
There is an option available for Mass Payments, which allows payment initiation to different payees, via different payment channels, all at once. 

### 6. Virtual Card: 
This is a set of four APIs that allows a customer to add a vitual card to their account (with the limit and expiration date of their choice), update limit at a later time, disable and enable the card at will, as well as on-demand expiration of the card. 

### 7. Profile Update:
There are APIs available to update customer as well as payee profiles. Personal information such as address, email address and phone number can be changed.

### 8. Account closure:
There are a couple APIs present in this set, that allow for closure of all accounts for a customer at the same time, or only a particular account.

### 9. Administrative APIs:
Besides the transactional APIs, there is a set of admin APIs available for balance inquiry, transaction history, Get APIs for account details, customer details, beneficiary details, and payment channel details, unlocking funding source.

<!-- Related links section: still REQUIRED but moved to toc file (in your same folder).  Edit there.
-->
