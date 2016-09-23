{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with Car Diagnostic API
{: #gettingstarted}
<!-- Provide an appropriate ID above -->
*Last updated: 22 September 2016*
{: .last-updated}

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->
This API can help you to assess the health status of a vehicle, by translating OBD error codes in a human readable form. This service is of great interest for various companies, e.g., IoT/Automotive startups, fleet management providers, booking platforms and taxi companies. We support all error codes that can be read with the widely used ELM327 OBD dongles. In addition to that, we also support error codes that are specific to car manufacturers. Our database includes more than 17.000 error codes that are professionally maintained.
{:shortdesc}

<!-- If overview content is required, do not include it here. Put it in a separate "## About" section below the task section. -->

<!-- Task section: REQUIRED
The task section includes steps to integrate the service into the app.  
- With task-based, technical information, reduce the conversational style in favor of succinct and direct instructions.
- DO include the basic, most-common-use scenario steps to use the service or integrate it into the app. 
- DO NOT include steps to add the service from the Bluemix catalog; we assume that the user already took steps in the UI to add the service. 
- DO include code snippets in all languages that can be copied, as well as VCAP service info.  
- For additional tasks like configuring, managing, etc., add a task section (## Gerund_task_title) below the task section or "About" section if used. Use a task title such as "Configuring x", "Administering y", "Managing z". -->

## Setting up Car Diagnostic API
<!-- You can include an optional prerequisites paragraph for any prerequisites to be met before integrating the service. For example: -->

This API assumes that you already know how to read error codes from the OBD port
of a car. The example Apps in the Related Links section below can show you how
to do this in Android and Swift.

<!-- Include a sentence to briefly introduce the steps. Examples: -->

To get up and running quickly with this service, follow these steps:

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

1. Go to the Internet of Things section in the Bluemix catalog and click on the
   "Car Diagnostic API" tile.
2. Click on "Register at Car Diagnostic API".
3. Create a new account in this IBM Developer Portal page.
4. Create a new developer organization.
5. Go to "Apps" and click on "Register new Application"
6. Enter a title for the App and a decription (optional).
7. Write down your Client Secret and your Client ID. These are the
   username/password that you will use to access the API. Note that the Client Secret is displayed only once on this page.
8. Go to "API Products" and click on "Car Diagnostic API".
9. Choose a plan and click on "Subscribe".
10. Select an App and click on "Subscribe".
11. Go to the "Car Diagnostic API" section on the left side of this page. There
    you can try out the API and get instructions on how to call the API - these
    include the URL for calling the API. In addition you can find here coding
    examples in different programming languages that exemplify how to call the
    API. Note that the Client ID and Client Secret need to be passed to the API
    as query parameters for authentication.

When you go back to the initial Bluemix screen of the Car Diagnostic API, you
can enter the Client ID and Client Secret in the corresponding fields and press
on "Create". After that the Client ID and Client Secret are available in the
VCAP_SERVICES environment variable, so that any App that is bound to this
service can access them.

<!-- Related links section: REQUIRED.
Related links display in the upper right of the getting started page. 
Ensure that you retain the lowercase anchor IDs (eg. {: #rellinks}) as shown in this template. These are used as IDs during transform and the doc framework keys off the IDs for display. 
The headings coded here are not actually used. The doc framework provides the correct headings. 
Also ensure that the related links stay in position at the end of this file or the doc framework will not display them properly.
Use {:new_window} for external links to open a new window.-->
<!-- Please delete all comments within the related links section to avoid breaking the build. Thanks. -->

# Related Links
{: #rellinks}

## Tutorials and Samples
{: #samples}

<!-- Recommended external links to your top three devWorks articles and sample applications. NOTE: sample apps should be in node and java at a minimum. Link text should be: <sample_name> sample or developerworks: <article_name>. To confirm the available articles for your service, go to http://www.ibm.com/developerworks/views/global/libraryview.jsp?show_abstract=falsecontentarea_by=All+Zonesproduct_by=-1topic_by=BlueMixindustry_by=-1type_by=All+Typesibm-search=Search and select your service from the product drop-down menu -->

* [iOS OBD Example App](https://github.com/HellaVentures/iOS-OBD-Example-App){:new_window}
* [Android OBD Example App](https://github.com/HellaVentures/Android-OBD-Example-App){:new_window}


## API Reference
{: #api}

<!-- External links to the landing page of each generated doc for the APIs that are supported by your service. Use only the type of API as the link text (Java, JavaScript, REST, Objective-C) -->

* [API Documentation](https://github.com/HellaVentures/Car-Diagnostic-API){:new_window}

## Related Links
{: #general}

<!-- Include a link to your full product documentation, pricing sheet, IBM Bluemix prerequisites -->
<!-- NOTE: Remove these comments when using this template. Otherwise the comment will break the build! Thanks. -->

* [IBM Developer Portal](https://production-hella-ventures-car-diagnostic-api.developer.eu.apiconnect.ibmcloud.com/user/register){:new_window}
