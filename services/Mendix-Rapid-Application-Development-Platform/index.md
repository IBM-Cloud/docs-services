---

copyright:

  years:  2017

lastupdated: "2017-10-18"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with Mendix Platform on IBM Cloud 
{: #gettingstarted}
<!-- Provide an appropriate ID above -->

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->

Mendix Platform is a Low-code development platform which allows you deliver Multi device applications faster with less resources runnon on IBM Cloud platform. 

<!-- If overview content is required, do not include it here. Put it in a separate "## About" section below the task section. -->

<!-- Task section: REQUIRED
The task section includes steps to integrate the service into the app.  
- With task-based, technical information, reduce the conversational style in favor of succinct and direct instructions.
- DO include the basic, most-common-use scenario steps to use the service or integrate it into the app. 
- DO NOT include steps to add the service from the Bluemix catalog; we assume that the user already took steps in the UI to add the service. 
- DO include code snippets in all languages that can be copied, as well as VCAP service info.  
- For additional tasks like configuring, managing, etc., add a task section (## Gerund_task_title) below the task section or "About" section if used. Use a task title such as "Configuring x", "Administering y", "Managing z". -->

<!-- You can include an optional prerequisites paragraph for any prerequisites to be met before integrating the service. For example: -->

Before you get started developing your first application using the Mendix Platform, there are a few steps you'll need to follow in order to deploy your app to IBM Bluemix.


<!-- Include a sentence to briefly introduce the steps. Examples: -->

Mendix runs on Cloud Foundry in the IBM Bluemix PaaS so you're going to need the following information to configure your Bluemix account.

- API End Point
- IBM Bluemix Username and Password

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

## 1. Step 1 Start the Mendix Boilerplate 
To quickly setup your application enviroment within IBM Bluemix, you can use the Mendix Rapid Apps [Boilerplate](https://console.bluemix.net/catalog/starters/mendix-rapid-apps?env_id=ibm%3Ayp%3Aeu-gb&taxonomyNavigation=apps)


## 2. Step 2 Signup for free

First you'll need a Free Mendix account. It takes less than a minute, and the only data we'll need to get you started is your name and email address. https://www.mendix.com/try-now

## 3. Step 3 Follow the guided tutorial

Mendix will guide you through the development of your first rapid app. Just follow the instructions in the platform and modeler, and you'll have your first fully responsive app up and running in no time.

## 4. Step 4 Deploying to IBM Bluemix

At several points during the guidance you'll be asked to Run in Sandbox. Sandboxes are free Mendix Cloud slots.

## 5. Step 5 Setup IBM Bluemix deployment

Mendix runs on top of Cloud Foundry in the IBM Bluemix PaaS. First of all you need to configure your Cloud Foundry settings.

Mendix will automatically test the connection to make sure we've made contact with your account.

### a. Select the boilerplate
Choose 'Select existing app' and select the app you created using the 'Mendix Rapid Apps' Boilerplate

## 5. Step 5 Deploy
Now you're connected you can run your app on IBM Bluemix by clicking on 'Run on Cloud Foundry'

Remember, you'll need to 'Run on Cloud Foundry' to test your application.

<!-- Related links section: still REQUIRED but moved to toc file (in your same folder).  Edit there.
-->