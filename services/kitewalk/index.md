---

copyright:

  years:  2017

lastupdated: "2017-06-29"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with Kitewalk GEO Web Services
{: #gettingstarted_kitewalk}

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->

Kitewalk GEO Web Services for Bluemix add geo-intelligence features to your apps ("around me" functionalities). Using Kitewalk, your apps can set and get contents of any nature both timely and spatially. Ultimately, Kitewalk will allow to retrieve lists of dynamic geo-contents within distance, time and category of interest constraints around any GPS position.
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

Kitewalk technology and its use cases are described in [this video](https://youtu.be/ll3GT-sRwB0). Before an application developer can embed Kitewalk capabilities into an app, the administrator will need to specify its Kitewalk API Id and its Kitewalk API Key inside the Bluemix user interface.

<!-- Include a sentence to briefly introduce the steps. Examples: -->

To integrate your app with Kitewalk GEO Web Services, complete these steps:

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

1. Registration to Kitewalk GEO Web Services -> follow the instructions included in our [First Steps Guide](http://api.kitewalk.com#first-login)
2. Initial tests of Kitewalk GEO Web Services-> follow the instructions included in our [First Tests Guide](http://api.kitewalk.com#first-tests)

	```
	Testing the services is free. A sandbox/testing API ID and API KEY will be provided for such purpose.
	The sandbox/testing site at http://ws.kitewalk.com will also help developpers to debug/inspect API calls.
	```
	{: codeblock}

3. Once the services will be mastered in the sandbox/testing environment, a production (API ID, API KEY) couple can be requested to Kitewalk at any time. Such production keys will allow the use of Kitewalk GEO Web Services in a fully independent single-tenant environment which can be fully customized to meet the customer requirements in terms of categories of contents, time and distances. The Kitewalk API Id and its Kitewalk API Key inside the Bluemix user interface will need to be updated accordingly.

<!-- 
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

 -->

<!-- Related links section: REQUIRED but moved to toc file (in your same folder).  Edit there by adding the following: -->

{: .navgroup id="learn"}
    index.md

    {: .topicgroup}
    Related links
        [IBM Blog entry](http://api.kitewalk.com)
        [Use Cases](http://kitewalk.com/index#use)
        [Pricing](http://kitewalk.com/offer#pricing)
    {: .navgroup-end}

<!-- To add related links, indent the 8 spaces, put the name of the link in [] and the URL in (), like so:
        [Link text](https://pathtolink.html)
    
If you have API references to add, leave a blank line under the previous navgroup and then add: -->

    {: .navgroup id="reference"}
    Reference
        [API Documentation](http://api.kitewalk.com)
    {: .navgroup-end}
