---

copyright:

  years:  2017

lastupdated: "2017-07-25"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with Zuznow
{: #gettingstarted_Zuznow}

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->

Zuznow provides an automatic mobile adaptation platform that adapts even the most complex web applications to mobile apps Using Zuznow platform, once can fully preserve the original application’s user experience, content, functionality, and business logic. Zuznow platform is composed of an automatic responsive engine, which runs CSS and style changes - on the fly and in real-time on the entire application, creating a mobile app in an instant; and of an adaptive engine - which offers a full featured customization dashboard (the Editor) that web developers can use to customize the automatic result, using simple CSS, HTML and jQuery commands.

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

Complete these steps to get started with the Zuznow service:

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

1. Register at Zuznow
Enter your Dashboard username and password and click Log in. If you don’t have a user, you can create a new one or log in using your Google account.

2. Create a new site
Select New App in the Dashboard side menu to access the wizard where you define a new mobile app.

3. Define the following parameters for the new mobile site:
a. App Parameters
Define the following parameters for the new mobile app: App Name: Enter your App project name. This can be any text Domain: The URL of the application domain to be mobilized. Click the Next button to define the App Features
b. App Features
Automatic Responsive Design: choose Enabled to allow automatic responsive design
Tablet support: choose Enabled to allow customized Tablet support for your app
Cache: choose personalized or anonymous depending on the original application
SSL Support: choose Enabled for SSL encrypted communication
Click Create to automatically build your mobile app. Congratulations - your app is ready!
4. Copy your app credentials
From “My Apps” tab, open your new application, and copy the App ID and API Key to the Bluemix console



<!-- Related links section: REQUIRED but moved to toc file (in your same folder).  Edit there by adding the following:

{: .navgroup id="learn"}
    index.md

    {: .topicgroup}
    Related links
        [Visit our support forum]https://zuznow.atlassian.net/wiki
	[Submit a ticket to consult our experts]https://zuznow.atlassian.net/servicedesk/customer/portal/1
	[Read the latest from Zuznow's blog]https://www.zuznow.com/blog/
    {: .navgroup-end}
    
    {: .navgroup id="reference"}
    Reference
        [API Clients](https://github.com/zuznow?tab=repositories)
    {: .navgroup-end}
-->
