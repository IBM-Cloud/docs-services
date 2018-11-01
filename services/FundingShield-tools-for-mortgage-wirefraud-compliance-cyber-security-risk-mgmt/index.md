{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About FundingShield API
{: #gettingstarted}

FundingShield is the market leading fintech firm offering plug’n play, scalable, cloud-based risk, compliance and fraud technology solutions to protect the Mortgage, Real Estate, Title, and Legal industries from wire fraud, social engineering attempts, injection attacks, and regulatory and compliance risk with third parties. Fundingshield’s cost and time effective solutions deliver the highest level of control and risk mitigation helping you improve your bottom line.  Further we do not provide a data bank, we deliver actionable intelligence at the loan level so our clients make more informed decisions with full understanding of the risk.

{:shortdesc}

## Getting started

Contact sales@fundingshield.com and obtain credentials for the WAVS API Documentation and Subscription Key.

@ECHO OFF

curl -v -X POST "https://api.fundingshield.com/wavs/wavs"
-H "Content-Type: application/json"
-H "Ocp-Apim-Subscription-Key: {subscription key}"

--data-ascii "{body}"