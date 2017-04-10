---

copyright:

  years: 2016

lastupdated: "2016-09-22"  

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Getting started with Car Diagnostic API
{: #gettingstarted_HellaVentures}

This API can help you to assess the health status of a vehicle, by translating OBD error codes in a human readable form. This service is of great interest for various companies, for example, IoT/Automotive startups, fleet management providers, booking platforms and taxi companies. We support all error codes that can be read with the widely used ELM327 OBD dongles. In addition to that, we also support error codes that are specific to car manufacturers. Our database includes more than 17.000 error codes that are professionally maintained.
{:shortdesc}


## Setting up Car Diagnostic API

This API assumes that you already know how to read error codes from the OBD port
of a car. The example Apps in the Related Links section below can show you how
to do this in Android and Swift.

To get up and running quickly with this service, follow these steps:

1. In the "Bluemix catalog", go to the "Internet of Things" section and click on
   the "Car Diagnostic API" tile.
2. On the next page, click on the "Register at Car Diagnostic API" link.
3. The next page is the IBM Developer Portal of this API. On this page, click on
   the "Login" link in the top right. After you have been logged in, enter a
   name for your Developer Organization (e.g. my-dev-org).
4. Next, go to "Apps" and click on "Register new Application"
5. Enter a title for the App and a description (optional).
6. Write down your Client Secret and your Client ID. These are the
   username/password that you will use to access the API. Note that the Client
   Secret is displayed only once on this page. The Client Secret is located at
   the top of the page and the Client ID on the bottom - you need to click the
   checkboxes to make them visible
7. Go to "API Products" and click on "Car Diagnostic API".
8. Choose a plan and click on "Subscribe". In the next pop-up window select an App
   and click on "Subscribe".
9. Go to the "Car Diagnostic API" section on the left side of this page. There
   you can try out the API and get instructions on how to call the API - these
   include the URL for calling the API. In addition you can find here coding
   examples in different programming languages that exemplify how to call the
   API. Note that the Client ID and Client Secret need to be passed to the API
   as query parameters for authentication.

When you go back to the initial Bluemix screen of the Car Diagnostic API, you
can enter the Client ID and Client Secret in the corresponding fields. If you
have not also bound your service instance, you will have to bind your new
service instance to one or more Bluemix applications. Once the Bluemix
applications have been restarted or restaged, the Car Diagnostic API Client ID
and Secret will be available within the application's VCAP_SERVICES environment
variable.


<!-- Related links section moved to toc:

# Related Links
{: #rellinks notoc}

## Tutorials and Samples
{: #samples}

* [iOS OBD Example App](https://github.com/HellaVentures/iOS-OBD-Example-App){:new_window}
* [Android OBD Example App](https://github.com/HellaVentures/Android-OBD-Example-App){:new_window}


## API Reference
{: #api}

* [API Documentation](https://github.com/HellaVentures/Car-Diagnostic-API){:new_window}

## Related Links
{: #general}

* [IBM Developer Portal](https://production-hella-ventures-car-diagnostic-api.developer.eu.apiconnect.ibmcloud.com/){:new_window}
-->
