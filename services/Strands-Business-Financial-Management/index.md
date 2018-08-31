---

copyright:

  years:  2018

lastupdated: "2018-06-29"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}


# Getting started with BFM
{: #gettingstarted}

Strands Business Financial Management (BFM) is a service that helps SMEs to better manage their finances. With the service you will be able to manage transactions, invoicing, cash flow analysis, income & expenses, financial calendar, budgetting, provisioning and more.

{:shortdesc}

To learn more about Strands Business Financial Management, visit our [website](https://finance.strands.com/products/bfm-business-financial-management/){:new_window}.

Before an application developer can start using the BFM API, they need to request access first.

1. Request access to the BFM API environment, by filling [this](https://finance.strands.com/request-demo-ibm/) form
2. Once you have submitted your request, and Strands representative will reach out to you and provide the appropriate API credentials by email.
3. The email will contain further details allowing you to:

    - Access to the online documentation, with all the available API's listed, which can be run directly from the documentation providing all the different responses
    - Access to a sample UI implementation using the available API's

# Overview
{: #overview}

Once the onboarding process is completed, you can start consuming the different APIs.

These would be organized into different categories within the online documentation.


## Authentication
{: #authentication}

To authenticate, please just follow the instructions provided in the email containing your API credentials.
 
On one hand you would get your authorization token, that would allow to access the API environment. In addition to that, you would need to provide also the customer identification, on whose behalf requests will be performed.


## Example
{: #example}

The following is just and example of a request to one of the endpoints, that you could explore further in the online documentation.

Below we are retrieving latest 5 transactions from a customer, without applying any further filtering.
Notice we are passing in a ´authorization´ header, where you should be using the API KEY you will receive by email. Also you can see the ´HTTP_STRANDS_USER´ header regarding the customer performing the request, as explained earlier.

	```
	curl -X GET --header 'Accept: application/json' --header 'authorization: YOUR_API_KEY_HERE' --header 'HTTP_STRANDS_USER: testUserBU1' 'https://api.strands.com/fm-api/api/transactions?currentPage=1&pageSize=5'
	```
	{: pre}

The above call will get back a response as follows:

	```
	{
      "response": {
        "code": 200,
        "message": "OK"
      },
      "result": {
        "currentPage": 1,
        "nextPage": 2,
        "totalPages": 519,
        "totalElements": 2592,
        "data": [
          {
            "accId": 72,
            "id": 10293,
            "name": "Cart REF. O0050",
            "amount": 59,
            "postedDate": "2018-06-28",
            "postedDateStr": "2018-06-28",
            "catId": 202,
            "computable": true,
            "realName": "Cart REF. O0050",
            "cuxAmount": 66.29,
            "currency": "USD",
            "split": false,
            "ticked": false,
            "linkedToOrFromCash": false,
            "accProvId": "72",
            "accRealName": "XXX-123-XXX-XX",
            "accName": "Checking Account 0000000111",
            "accType": 4,
            "entId": 3,
            "entName": "Cash Account",
            "providerId": "10293",
            "parentCatId": 201,
            "recurringMatched": false,
            "alertsPending": false,
            "forecast": false,
            "cuxAmnt": 66.29,
            "transactionDate": "2018-06-28"
          },
          {
            "accId": 73,
            "id": 10917,
            "name": "Google Services",
            "amount": -155,
            "postedDate": "2018-06-28",
            "postedDateStr": "2018-06-28",
            "catId": 254,
            "computable": true,
            "realName": "Google Services",
            "cuxAmount": -155,
            "currency": "EUR",
            "split": false,
            "ticked": false,
            "linkedToOrFromCash": false,
            "accProvId": "73",
            "accRealName": "1234 **** **** ****",
            "accName": "Credit Card 0000000111",
            "accType": 1,
            "entId": 3,
            "entName": "Cash Account",
            "providerId": "10917",
            "parentCatId": 243,
            "recurringMatched": false,
            "alertsPending": false,
            "forecast": false,
            "cuxAmnt": -155,
            "transactionDate": "2018-06-28"
          },
          {
            "accId": 74,
            "id": 11574,
            "name": "Moto-Accessories Inc.",
            "amount": -500,
            "postedDate": "2018-06-28",
            "postedDateStr": "2018-06-28",
            "catId": 227,
            "computable": true,
            "realName": "Moto-Accessories Inc.",
            "cuxAmount": -500,
            "currency": "EUR",
            "split": false,
            "ticked": false,
            "linkedToOrFromCash": false,
            "accProvId": "74",
            "accRealName": "**** **** 1234 ****",
            "accName": "Prepaid Card 0000000111",
            "accType": 9,
            "entId": 3,
            "entName": "Cash Account",
            "providerId": "11574",
            "parentCatId": 226,
            "recurringMatched": false,
            "alertsPending": false,
            "forecast": false,
            "cuxAmnt": -500,
            "transactionDate": "2018-06-28"
          },
          {
            "accId": 72,
            "id": 10283,
            "name": "Electricity Company",
            "amount": -150,
            "postedDate": "2018-06-28",
            "postedDateStr": "2018-06-28",
            "catId": 223,
            "computable": true,
            "realName": "Electricity Company",
            "cuxAmount": -168.54,
            "currency": "USD",
            "split": false,
            "ticked": false,
            "linkedToOrFromCash": false,
            "accProvId": "72",
            "accRealName": "XXX-123-XXX-XX",
            "accName": "Checking Account 0000000111",
            "accType": 4,
            "entId": 3,
            "entName": "Cash Account",
            "providerId": "10283",
            "parentCatId": 218,
            "recurringMatched": false,
            "alertsPending": false,
            "forecast": false,
            "cuxAmnt": -168.54,
            "transactionDate": "2018-06-28"
          },
          {
            "accId": 72,
            "id": 10292,
            "name": "Cart REF. O0049",
            "amount": 390,
            "postedDate": "2018-06-28",
            "postedDateStr": "2018-06-28",
            "catId": 202,
            "computable": true,
            "realName": "Cart REF. O0049",
            "cuxAmount": 438.2,
            "currency": "USD",
            "split": false,
            "ticked": false,
            "linkedToOrFromCash": false,
            "accProvId": "72",
            "accRealName": "XXX-123-XXX-XX",
            "accName": "Checking Account 0000000111",
            "accType": 4,
            "entId": 3,
            "entName": "Cash Account",
            "providerId": "10292",
            "parentCatId": 201,
            "recurringMatched": false,
            "alertsPending": false,
            "forecast": false,
            "cuxAmnt": 438.2,
            "transactionDate": "2018-06-28"
          }
        ]
      }
    }
	```
	{: screen}