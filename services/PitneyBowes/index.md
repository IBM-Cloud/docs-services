---

copyright:

  years: 2016, 2017

lastupdated: "2016-09-08"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}


# Getting started with Pitney Bowes APIs
{: #gettingstarted}

Pitney Bowes APIs allow any developer to access enterprise-class solutions for applications ranging from business intelligence to customer engagement and commerce. These solutions are used by leading companies in industries such as banking, insurance and retail, enabling end users to make the best decisions and achieve the best business outcomes. Now available to developers through modern REST APIs, developers in any size organization can access these class-leading tools and datasets, rapidly deploying and scaling solutions.
{:shortdesc}

The APIs are broadly categorized into the following categories:
* Identify: Break down names and addresses, correct and validate your data, then add insight about your customers.
* Locate: Add context to locations through highly accurate and comprehensive datasets. Unlock deeper insight, orchestrate workflows, or engage customers more effectively through mix-in and mash-up geodata.
* Communicate (Coming soon): Enable multi-channel communications with clients or prospects.
* Ship: Add feature-rich USPS shipping capabilities to eCommerce or IoT applications. It's shipping, made simple.
* Pay: Charge accurate import duty and taxes at checkout and offer a total landed cost to your international customers.

## Before you begin

Ensure that you have the Cloud Foundry CLI installed on your computer. The CLI is available here: [https://github.com/cloudfoundry/cli#downloads](https://github.com/cloudfoundry/cli#downloads){:new_window}. After the CLI is installed, you'll be able to use the cf command from your command line interface.

## Setting up Pitney Bowes APIs

To add APIs from Pitney Bowes' service to your Bluemix application, follow these steps:

1. Set up the Bluemix API endpoint:

  ```
  cf api https://api.ng.bluemix.net
  ```
  {: codeblock}
  
2. Log in to Bluemix with your Bluemix credentials:

  ```
  cf login
  ```
  {: codeblock}
  
3. Choose your organization and space, and create a service instance in your selected space. For example, using `pitneybowes free` as the service and `mypitneybowes01` as the service instance name, you would type:

  ```
  cf create-service PitneyBowes-APIs free mypitneybowes01
  ```
  {: codeblock}
  
4. Bind your Pitney Bowes API instance to your application. For example, by using `MyApp` as your application and `mypitneybowes01` as your service instance, type the following command:

  ```
  cf bind-service MyApp mypitneybowes01
  ```
  {: codeblock}
  
5. Optionally, to validate that the service is bound to your application, use the `cf services` command. 

6. After Pitney Bowes APIs are bound to your application, the specific configuration of your Pitney Bowes APIs appears in your environment variable. To list the details, use the `cf env` command followed by your application name, for example:
  ```
  cf env MyApp
  ```
  {: codeblock}
  
## Using the Pitney Bowes APIs

The credentials block provides everything you need to use the APIs from Pitney Bowes.
* apiKey: Your key for accessing the Pitney Bowes API
* apiSecret: The secret for accessing the Pitney Bowes API

To get started using the Locate & Identify APIs, see the [API QuickStart](https://locate.pitneybowes.com/docs/location-intelligence/v1/en/index.html#Getting%20Started/getting_started.html){:new_window}, the [Locate API Specification](https://locate.pitneybowes.com/docs/location-intelligence/v1/en/index.html#Product%20Overview/apis.html){:new_window} and the [Identify API Specification](https://identify.pitneybowes.com/docs/identify/v1/en/rest/index.html#CustomerInformationManagementAPI/source/API/IdentifyAddress/ValidateMailingAddress.html){:new_window}.
