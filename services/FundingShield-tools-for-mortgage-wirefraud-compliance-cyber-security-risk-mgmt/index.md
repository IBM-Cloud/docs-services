---

copyright:

  years:  Invalid Date

lastupdated: "Invalid Date"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About FundingShield tools for mortgage wire-fraud, compliance, & cyber security risk mgmt
{: #gettingstarted}

FundingShield is the market leading fintech firm offering plug’n play, scalable, cloud-based risk, compliance and fraud technology solutions to protect the Mortgage, Real Estate, Title, and Legal industries from wire fraud, social engineering attempts, injection attacks, and regulatory and compliance risk with third parties. Fundingshield’s cost and time effective solutions deliver the highest level of control and risk mitigation helping you improve your bottom line.  Further we do not provide a data bank, we deliver actionable intelligence at the loan level so our clients make more informed decisions with full understanding of the risk.

{:shortdesc}

## Getting started

Contact Sales and obtain a username and password for the WAVS API Documentation.

Contact help@fundingshield.com and requests a WAVS  API subscription key.

@ECHO OFF

curl -v -X POST "https://api.fundingshield.com/wavs/wavs"
-H "Content-Type: application/json"
-H "Ocp-Apim-Subscription-Key: {subscription key}"

--data-ascii "{body}"

