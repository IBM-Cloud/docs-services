---

copyright:

  years:  2018

lastupdated: "2018-06-28"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About AccountScore
{: #gettingstarted}

AccountScore is an analytics business based in London but with people in the USA and in India, which provides actionable insights and analytics on bank transaction data for our clients - typically banks and financial services companies who want to learn more about their customers, prospects and applicants.

Where our clients already have bank transaction data we simply import the data and provide analytics through our dashboards or by API. Accounts can be analysed individually, or we can process multiple accounts with millions of transaction rows in a single import.

Where our clients are non-banks that want to analyse bank data for their customers, or banks that want to analyse their customers’ transactions from other banks, we work with our sister company, consents.online, which obtains and stores transactions for clients and manages customers’ permissions for the viewing of this data. consents.online is a Registered Account Information Service Provider (AISP) with the Financial Conduct Authority, registration number 792642.

consents.online is a place where customers can control what consents they have given and to whom. Where consent has been granted, it connect to banks to collect the transaction data that our clients request. [Learn more about consents.online](https://consents.online){:new_window}

Clients of AccountScore can use consents.online on a back-to-back basis so do not need a direct contractual relationship with it.

{:shortdesc}

## Getting started

There are two aspects to an AccountScore integration.  Data collection via our application form and data ingestion via either our APIs or our dashboards.

In its default mode, AccountScore will use the Yodlee account aggregation API to extract transaction data from a customer's online bank account. To do this, we use a secure iFrame to collect internet banking credentials from the customer which are then passed to Yodlee who extract the transaction data and return it to AccountScore for analysis.  In the UK we are a registered AISP and can access bank transaction data directly from the Open Banking APIs.

Our Enrich API allows you to upload transactions directly to our platform and Enrich will return richly categorized data as well as numerous actionable insights via API.

Our Forecasting API provides both quarterly and monthly views of the data collected from commercial bank accounts. Data is separated into credits and debits, with each sector then sub-divided into recurring, repeating, significant or other classes.

## Obtaining Credentials

Before you will be able to use the AccountScore platform you will need to contact a member of our sales team (enquiries@accountscore.com) to discuss your individual requirements.  You will be provided with a set of credentials for our sandbox environment along with an API key.

## AccountScore API

A full [integration guide](https://www.accountscore.com/api){:new_window} detailing the functionality of our RESTful API is available on the Accountscore website.