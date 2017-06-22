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

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with Skyhook Precision Location
{: #gettingstarted_SkyhookLocation}

The Skyhook Precision Location API provides access to positioning information derived from the analysis of positioning anchors including Wi-Fi access points, cell IDs and others in known locations. The client applications make XML-over-HTTPS calls to the API while providing a listing of observed positioning anchors within range of the client device, along with GPS information if available. The Location Server API returns a calculated geographic location based on those inputs, and optionally a street address and time zone.

In addition to the derived location the API returns location based on the client's IP address. While this information is not a reliable source for navigation, it can be used to provide context in the event that more accurate methods are not available, it may be used as the best estimate of location.

{:shortdesc}

<!-- If overview content is required, do not include it here. Put it in a separate "## About" section below the task section. -->

<!-- Task section: REQUIRED
The task section includes steps to integrate the service into the app.  
- With task-based, technical information, reduce the conversational style in favor of succinct and direct instructions.
- DO include the basic, most-common-use scenario steps to use the service or integrate it into the app. 
- DO NOT include steps to add the service from the Bluemix catalog; we assume that the user already took steps in the UI to add the service. 
- DO include code snippets in all languages that can be copied, as well as VCAP service info.  
- For additional tasks like configuring, managing, etc., add a task section (## Gerund_task_title) below the task section or "About" section if used. Use a task title such as "Configuring x", "Administering y", "Managing z". -->

<!-- You can include an optional prerequisites paragraph for any prerequisites to be met before integrating the service. For example: -->

Before an application developer can embed single sign-on capability into an app, the administrator must create unbound service instances by using the Bluemix user interface.

<!-- Include a sentence to briefly introduce the steps. Examples: -->

To integrate your app with the service, complete these steps: -OR-
To get up and running quickly with this service, follow these steps: -OR-
Complete these steps to get started with the BigInsights service:

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

1. Step 1 to integrate app with the service.
2. Step 2 to integrate app with the service.

	```
	Copyable example for this step. 
	This example might be multiline code
	to copy into a file. 
	When displayed in the doc framework, 
	it will have a copy button on the right.
	The user can click to copy the example 
	so they can paste it into their code editor.
	```
	{: codeblock}

3. Step 3. In this step, we have a single line command example. When displayed by the doc framework, it will have a $ shown at the beginning of the line, and a copy button on the right. The copy button will copy the command but not the $.

	```
	my command -and -options
	```
	{: pre}

4. Step 4
	```
	This is a bunch of output from
		a command or program I ran
			and it can run lots of lines
			and the doc framework will show it as 
			output with no copy button.
	```
	{: screen}



<!-- Related links section: REQUIRED but moved to toc file (in your same folder).  Edit there by adding the following:

{: .navgroup id="learn"}
    index.md

    {: .topicgroup}
    Related links
        [Link text](URL)
    {: .navgroup-end}

To add related links, indent the 8 spaces, put the name of the link in [] and the URL in (), like so:
        [Link text](https://pathtolink.html)
    
If you have API references to add, leave a blank line under the previous navgroup and then add:

    {: .navgroup id="reference"}
    Reference
        [API Documentation](https://pathtolink.html)
    {: .navgroup-end}
-->
