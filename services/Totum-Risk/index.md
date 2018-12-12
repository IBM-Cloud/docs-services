---

copyright:

  years:  2018

lastupdated: "2018-12-12"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About Totum Risk
{: #gettingstarted}

Totum Risk provides a unique risk tolerance tool for financial advisers that calculates how much risk an investor can take given their current life situation (risk capacity) instead of the traditional model that only looks at how much risk an investor wants to take (risk preference).

The API services allows  developers to build a complete Risk tool that can create questionnaire , get  risk score, risk capacity, score portfolios and  get analytics data on the portfolios. 

The API also supports enterprise customers with admin access to  manager advisers/users.

{:shortdesc}

## Getting started

To get started please visit our  sign up page 
https://web.totumrisk.com/public/signup and enter promo code TRIAL for 1  day free trial.

Please refer to our Swagger documentation for more help and guidance on APIs
https://dev.platform.totumrisk.com/swagger/index.html

If you have questions please feel free to reach out to

In order to  use API services, first register with the website to get basic credentials. Use these credentials in the API to login. Sucessful login will return a  user token which would be used to access Totum API services.

For each API service, the request will need pre-authenticated token from Step 1.  The token will expire after 10 hours of inactivity. This API service is stateless.

Each token is associated with an advisor, who can then add clients, create a questionnaire, email the questionnaire, get questionnaire results and score the portfolios etc.

