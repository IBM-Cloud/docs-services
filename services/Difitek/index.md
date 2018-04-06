---

copyright:

Years:  2012, 2018

lastupdated: "2018-01-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}


# Getting started with Difitek
{: #gettingstarted}


Difitek is a powerful cloud-based, API-first platform for online finance applications. Customers can access end to end financial services functions through a single API and use them together with our Intelligent Connectivity Layer to create smart automated workflows.

{:shortdesc}

If you wish to integrate your app with our service, merely go to the following URL and follow the steps there: https://www.difitek.com/signup. From there, you will receive an email with a temporary API Key and Secret, which is required for any function to reach our API. Once an API Key and Secret have been made available, you merely have to plug in the calls according to the documentation found at www.difitek.com/api.

Examples of calls are as follows:

POST /organizations/{id}/capitalizations

This call will create a new Capitalization for an Organization, specified by the path parameter organization_id. This can be done through the Back Office application or directly through the API from your front-end platform.

Capitalizations are used in order to access the share registry features in the Back Office, which allow you to transfer shares from the Organization or individual Users to the investors in an Offering.

Before an application developer can perform the Create Capitalization function, the administrator must have approved and published the Organization as well as Offering to which the Capitalization refers to.


Sample Request Body for creating a Capitalization is as follows:

{
    "number_of_shares": "100",
    "price_per_share": "1",
    "owner_id" : "1098",
    "life_cycle_stage" : "1",
    "capitalization_type" : "0"
}

Another example call which can be used is the:

POST /offerings/{id}/dealRooms

This creates a deal room for a specific offering, similarly specified through the Offering ID in the call itself.
Implement this function to create a new Deal Room, which acts as the access-controlled area of an Offering that includes discussion forums, due diligence tasks, and access-restricted documents. Unlike the aforementioned Capitalization call, this function does not require any body parameters.