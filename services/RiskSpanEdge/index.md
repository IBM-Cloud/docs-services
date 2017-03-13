---

copyright:

  years:  2017

lastupdated: "2017-03-13"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with RiskSpanEdge
{: #gettingstarted}
<!-- Provide an appropriate ID above -->

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->
<!-- 
IBM Single Sign On is a policy-based authentication service for Bluemix. With Single Sign On, you can easily embed single sign-on capability in Node.js or Liberty for Java apps. -OR-
With IBM IoT Real-Time Insights on Bluemix, you can perform analytics on real-time data from your Internet of Things devices, and gain insights about their health and the overall state of your operations.  -OR-
Use IBM BigInsights for Apache Hadoop for Bluemix to provision enterprise-scale, multi-node big data clusters on the IBM SoftLayer cloud. After they are provisioned, you can manage and access these clusters from the BigInsights service.
-->
RS Edge is a data discovery and modeling tool which prrovides access to billions of rows of mortgage performance data.  Our proprietary search and retrieval technology and scalable back-end data center allows for fast querying and ad-hoc analysis on-demand. Analysis is combined with RiskSpan's proprietary projection models to enable forecasting of credit and prepayment performance.
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
<!--
Before an application developer can embed single sign-on capability into an app, the administrator must create unbound service instances by using the Bluemix user interface.
-->
<!-- Include a sentence to briefly introduce the steps. Examples: -->
RS Edge provides a REST api to the data and analytic engine. 
To integrate your app with the service, complete these steps: 
1) Obtain auth ID from RiskSpan
2) Create a bucketing criteria appropriate to your analysis
3) Select the required stress scenario.

REST api parameters:
- auth_key - your key for accessing the RS Edge API
- deal_name - name of the portfolio being analyzed (Please use the sample portfolio: ABANK)
- trade_date - analysis date (YYYYMMDD format, example 20
- bucket_key - RS Edge XML query format


<!-- Related links section: REQUIRED.
Related links display in the upper right of the getting started page. 
Ensure that you retain the lowercase anchor IDs (eg. {: #rellinks}) as shown in this template. These are used as IDs during transform and the doc framework keys off the IDs for display. 
The headings coded here are not actually used. The doc framework provides the correct headings. 
Also ensure that the related links stay in position at the end of this file or the doc framework will not display them properly.
Use {:new_window} for external links to open a new window.-->
<!-- Please delete all comments within the related links section to avoid breaking the build. Thanks. -->


## API Reference
{: #api}

<!-- External links to the landing page of each generated doc for the APIs that are supported by your service. Use only the type of API as the link text (Java, JavaScript, REST, Objective-C) -->

* [link text](URL){:new_window}

## Compatible Runtimes
{: #buildpacks}

<!-- MAY BE REMOVING THIS: Peer links to the Getting Started page of each runtime that is supported by your service. Use only the name of the runtime as the link text (Node.js, Liberty for Java, Ruby on Rails, Ruby Sinatra) -->

* [link text](URL)

## Related Links
{: #general}

<!-- Include a link to your full product documentation, pricing sheet, IBM Bluemix prerequisites -->
<!-- NOTE: Remove these comments when using this template. Otherwise the comment will break the build! Thanks. -->

* [link text](URL){:new_window}
* [link text](URL)
* [link text](URL)

