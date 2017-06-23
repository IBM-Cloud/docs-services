---

copyright:

  years:  2017

lastupdated: "2017-06-13"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Skyhook Precision Location
{: #gettingstarted_SkyhookLocation}

Skyhook Precision Location is a service on {{site.data.keyword.Bluemix}} that you can use to enable geolocation of all IoT device types. {:shortdesc}

## Overview
{:overview}

The Skyhook Precision Location API provides access to positioning information derived from the analysis of positioning anchors including Wi-Fi access points, cell IDs and others in known locations. The client applications make XML-over-HTTPS calls to the API while providing a listing of observed positioning anchors within range of the client device, along with GPS information if available. The Location Server API returns a calculated geographic location based on those inputs, and optionally a street address and time zone.

In addition to the derived location the API returns location based on the client's IP address. While this information is not a reliable source for navigation, it can be used to provide context in the event that more accurate methods are not available, it may be used as the best estimate of location.

To learn more about using Skyhook Precision Location, visit our [website](http://www.skyhookwireless.com){:new_window}.

## Before you begin
{:byb}

To start using Skyhook Precision Location, you must first sign up for an account and obtain an API key. Follow the steps below:

1. Create a new account [here](http://my.skyhookwireless.com)
2) Once registration is completed, you will be shown steps to create your first project
from your account dashboard.
3) Hovering over the “Start a New Project” card, select “Precision Location” as the project
type.
4) Name your project whatever you like. For API testing, you can select either Linux or
Android as your platform of choice when prompted on the interface.
5) Once your project is created, your API key will be displayed in the top right hand side of
your project dashboard.

## Getting Started
{:getting_started}

Once you've registered, there are a few easy steps to start performing locations.

1. First, review our comprehensive API Documentation{:new_window}.
2. Add code to your device that collects signal information needed to peform a geolocation. Supported signals include Wi-Fi, GPS, and Cell. 
3. Parse the signal information into the correct format required by Skyhook's Precision Location API (example XML is shown in the API Documentation).
4. Perfom the location request and receive the response.

## Getting Help
{:getting_help}

Support requests to Skyhook's sales support engineering team can be submitted [here](http://my.skyhookwireless.com) through your Skyhook account.



