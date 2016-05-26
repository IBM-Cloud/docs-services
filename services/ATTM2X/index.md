{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with AT&T M2X on Bluemix
{: #gettingstarted}
*Last updated: 24 May 2016*

AT&T M2X on Bluemix provides cloud based time-series data storage, device management, message brokering, event triggering, geo-fencing, and data visualization for connected devices. Collect and store data from device sensors onto the highly available M2X cloud, configure event based triggers that act on incoming data in real time, monitor device location, and create custom embeddable visualizations using M2X Dashboards.
{:shortdesc}

To get up and running quickly with AT&T M2X, once you've added the M2X service to your app follow these steps:

1. Choose an [M2X Client Library](https://m2x.att.com/developer/client-libraries) that suits your needs and add it to your dependencies. All libraries are open source and fully documented within their respective GitHub repositories. Please refer to the repository for your library of choice for usage instructions. For example, to add the [Ruby](https://github.com/attm2x/m2x-ruby) library add the following to your Gemfile:

	```
	gem 'm2x'
	```
	{: codeblock}
	
2. Require the 'm2x' library in any file you will be making requests to M2X. Ruby example:

	```
	require "m2x"
	```
	{: codeblock}

3. Obtain your _Master Key_ from the Master Keys tab of your [Account Settings](https://m2x.att.com/account#master-keys) screen.

4. Initialize the M2X client object using the Master API Key. Ruby example:

	```
	m2x = M2X::Client.new(<MASTER_API_KEY>)
	```
	{: codeblock}

To get started using the M2X API check out the full [API documentation](https://m2x.att.com/developer/documentation/v2/overview).

# Related Links
{: #rellinks}

## Tutorials and Samples
{: #samples}

* [Getting Started](https://m2x.att.com/developer/get-started){:new_window}
* [Managing API Keys](https://m2x.att.com/developer/tutorials/managing-api-keys){:new_window}
* [Device Onboarding](https://m2x.att.com/developer/tutorials/device-onboarding){:new_window}
* [Pushing Data to M2X](https://m2x.att.com/developer/tutorials/pushing-data){:new_window}
* [Retreiving Data from M2X](https://m2x.att.com/developer/tutorials/retrieving-data){:new_window}
* [Using M2X Event Based Triggers](https://m2x.att.com/developer/tutorials/triggers){:new_window}
* [SAMPLE APP: CleverFaucet - Raspberry Pi Water Usage Monitor](https://github.com/attm2x/m2x-sample-cleverfaucet){:new_window}
* [SAMPLE APP: Pimotion - Raspberry Pi Motion Detector/Security Camera](https://github.com/citrusbyte/pimotion){:new_window}

## SDK
{: #sdk}

* [Java](https://github.com/attm2x/m2x-java){:new_window}
* [Ruby](https://github.com/attm2x/m2x-ruby){:new_window}
* [Node.js](https://github.com/attm2x/m2x-nodejs){:new_window}
* [PHP](https://github.com/attm2x/m2x-PHP){:new_window}
* [Python](https://github.com/attm2x/m2x-python){:new_window}
* [See the full list of client libraries...](https://m2x.att.com/developer/client-libraries){:new_window}

## API Reference
{: #api}

* [AT&T M2X API Documentation](https://m2x.att.com/developer/documentation/v2/overview){:new_window}

## Related Links
{: #general}

* [AT&T M2X API Documentation](https://m2x.att.com/developer/documentation/v2/overview){:new_window}
* [M2X Tutorials](https://m2x.att.com/developer/tutorials){:new_window}
* [Sample Apps](https://m2x.att.com/developer/sample-code){:new_window}
* [Supported Platforms](https://m2x.att.com/developer/supported-platforms){:new_window}
* [Changelog](http://changelog-m2x.att.com/){:new_window}
* [Pricing](https://m2x.att.com/pricing){:new_window}
* [Showcase](https://m2x.att.com/explore/showcase){:new_window}
* [System Integrator Program](https://iotservices.att.com/integrators){:new_window}
