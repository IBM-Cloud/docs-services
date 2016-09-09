{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}


# Getting Started with Pitney Bowes APIs
{: #gettingstarted}

*Last updated: 08 September 2016*
{: .last-updated}

Pitney Bowes APIs allow any developer to access enterprise-class solutions for applications ranging from business intelligence to customer engagement and commerce. These solutions are used by leading companies in industries such as banking, insurance and retail, enabling end users to make the best decisions and achieve the best business outcomes. Now available to developers via modern REST APIs, developers in any size organization can access these class-leading tools and datasets, rapidly deploying and scaling solutions.
{:shortdesc}

The APIs are broadly categorized into following:
* Identify - Break down names and addresses, correct and validate your data, then add insight about your customers.
* Locate – Highly accurate and comprehensive datasets that add context to locations. Mix-in and mash-up geodata to allow you to unlock deeper insight, orchestrate workflows or engage more effectively customers.
* Communicate – Enable multi-channel communications with clients or prospects (Coming Soon)
* Ship - Add feature-rich USPS shipping capabilities to eCommerce or IoT applications - it's shipping made simple.
* Pay - Charge accurate import duty & taxes at checkout and offer a total landed cost to your international customers.

##Before you begin

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
  cf create-service PitneyBowes-APIs Free mypitneybowes01
  ```
  {: codeblock}
  
4. Bind your Pitney Bowes API instance to your application, for example, using `MyApp` as your application and `mypitneybowes01` is your service instance, you would type:

  ```
  cf bind-service MyApp mypitneybowes01
  ```
  {: codeblock}
  
5. Optionally, to validate that the service is bound to your application, use the `cf services` command. 

6. After Pitney Bowes APIs are bound to your application, the specific configuration of your Pitney Bowes APIs will appear in your environment variable. To list the details, use the `cf env` command followed by your application name, for example:
  ```
  cf env MyApp
  ```
  {: codeblock}
  
### Using the Pitney Bowes APIs

The credentials block provides everything you need to use the APIs from Pitney Bowes.
* apiKey - your key for accessing the Pitney Bowes API
* apiSecret - the secret for accessing the Pitney Bowes API

To get started using the API to transcode your media files, please see the [API QuickStart](https://developer2.pitneybowes.com/docs/location-intelligence/v1/en/index.html#Getting%20Started/getting_started.html){:new_window} and [the API Specification](https://developer2.pitneybowes.com/docs/location-intelligence/v1/en/index.html#Product%20Overview/apis.html){:new_window}.
