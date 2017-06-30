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

Skyhook Precision Location is a service on {{site.data.keyword.Bluemix}} that you can use to geolocate IoT devices. {:shortdesc}

## Overview
{:overview}

The Skyhook Precision Location API provides access to geolocation information calculated by comparing positioning anchors observed in the vicinity of the IoT device, to positioning anchors in the Skyhook Precision Location database.  Positioning anchors may include Wi-Fi access points, cell IDs and others. 

The client applications make XML-over-HTTPS calls to the API while providing a list of observed positioning anchors within range of the client device, along with GPS information if available. The Precision Location servers calculate geographic location based on those inputs, and optionally a street address and time zone.

The API also returns location calculated based on the client's IP address. While this information is not a reliable source for navigation, it can be used to provide context as a "best estimate" in the event that more accurate methods are not available.

To learn more about using Skyhook Precision Location, visit our [website](http://hubs.ly/H07V66F0){:new_window}.

## Before you begin
{:byb}

To start using Skyhook Precision Location, you must first sign up for an account and obtain an API key. To do so, follow the steps below:

1. Create a new account [here](http://hubs.ly/H07V59T0).
2. Once you're registered, the steps to create your first project from your account dashboard will be displayed.
3. Hovering over the “Start a New Project” card, select “Precision Location” as the project type.
4. Name your project whatever you like. For API testing, you should select Linux as the default platform when prompted on the interface.  [the actual platform does not need to be Linux]
5. Once your project is created, your API key will be displayed in the top right-hand side of your project dashboard.

## Getting Started
{:getting_started}

With the Precision Location API, the device must collect data about the radio signal environment, including Wi-Fi access point MAC addresses, cell IDs, and signal strengths. This data is then submitted using the Precision Location API. When accessible, include GPS location in your submissions along with Wi-Fi and cell IDs to improve location results, even when GPS is unavailable.  As of version 2.21 GPS switching has also been added to our server-side functionality. For full API documentation, including Wi-Fi and Cell capabilities, please contact Skyhook at support@skyhook.com. 

### IP Addresses
For API calls, always use the DNS. Using hard-coded IP addresses is not supported by Skyhook and could cause a failure to return location requests.

If all API calls are being forwarded from a centralized server before being sent to the Skyhook API end-point, the x-forwarded-for HTTP header must be used with the original IP address of the device making the request. For example:
```
Forwarded: for=192.0.2.60; proto=http; by=203.0.113.43
```

### Submitting a Device “Username”
You must submit a unique device ID, or “username”, for the end-user device with each unique location request.  Doing so will enable more accurate location results and impact redundancy of how your location data is processed and weighted for optimization.  In addition to improved location accuracy for your apps or devices, reporting and API performance may also be impacted if “username” is not provided.  Please note that these individual DeviceIDs are not stored permanently.  Rather, they are stored with a rotating hash in accordance with our user and commercial privacy policies.  

### Example

#### API Request
```
<LocationRQ xmlns="http://skyhookwireless.com/wps/2005"
            version="2.24"
            street-address-lookup="full">
<authentication version="2.2">
	<key key="YOUR API KEY HERE" username="DEVICE SERIAL NUM, MAC ADDRESS, OR OTHER UNIQUE ID HERE"/>
</authentication>
	<access-point>
		<mac>E01C413B9414</mac>			<!-- MAC address, capitlized with all seperators removed -->
		<ssid>SkyFi-Corp</ssid>			<!-- SSID of access point, if available -->
		<signal-strength>-66</signal-strength>	<!-- Observed signal strength of the access point, in decibels (dBm) -->
		<age>5</age>				<!-- Relative time, in ms, since this access point was scanned -->
	</access-point>
	<access-point>
		<mac>E01C413BD528</mac>
		<ssid>SkyFi-Corp</ssid>
		<signal-strength>-63</signal-strength>
		<age>6</age>
	</access-point>
	<access-point>
		<mac>E01C413BD514</mac>
		<ssid>SkyFi-Corp</ssid>
		<signal-strength>-68</signal-strength>
		<age>4</age>
	</access-point>
</LocationRQ>
```

#### API Response
```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<LocationRS version="2.24" xmlns="http://skyhookwireless.com/wps/2005">
	<location age="0" ncell="0" nlac="0" lap="-P0Y1M27D" nap="1">
		<latitude>42.351774</latitude>
		<longitude>-71.046730</longitude>
		<hpe>337</hpe>
		<street-address distanceToPoint="22.914528142">
			<street-number>89</street-number>
			<address-line>Pittsburgh St</address-line>
			<city>Boston</city>
			<postal-code>02210</postal-code>
			<county>Suffolk</county>
			<state code="MA">Massachusetts</state>
			<country code="US">United States</country>
		</street-address>
	</location>
</LocationRS>
```

#### Code snippet
```
curl -H "Content-Type: text/xml" -H "X-forwarded-for: 127.0.0.1" -d @location_rq.xml https://api.skyhookwireless.com/wps2/location
```


## Getting Help
{:getting_help}

Support requests to Skyhook's sales support engineering team can be submitted [here](http://hubs.ly/H07V59T0) through your Skyhook account or via email at support@skyhook.com.



