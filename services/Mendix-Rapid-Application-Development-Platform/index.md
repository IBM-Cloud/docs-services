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


<!-- Include a sentence to briefly introduce the steps. Examples: -->

To start developing a new application with the Mendix Platform, you can go to the Starter kids located in the hamburger menu of IBM cloud. There are starter kids available for both Mobile, Watson and Web Apps. 

By selecting a Mendix Low-code starter kit you will be guided to initiated your account on Mendix platform, start your project and setup your  environment in either Cloud Foundry or your Kubernetes cluster. 

During this setup you will be requested to select a Mendix Platform Service. A Lite plan is available for evaluation.

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

## 1. Select a starter kit 

You can select a Mendix Low-code starter kit from either the [Mobile](https://console.bluemix.net/developer/mobile/starter-kits/mobile-for-mendix), Watson or [Web](https://console.bluemix.net/developer/appservice/starter-kits/basic-web-for-mendix) category



## 2. Give you application a name

A default name is provided. 

## 3. Authorize IBM to create your project on Mendix Platoform

In case this is your first project you will be guided to the Mendix Platform to sign up and authorize IBM Cloud to create a new project on Mendix Platform on your behave. This project will be linked to IBM Cloud, so deployments will be automatically directed to IBM Cloud

## 4. Select your container type to run your application

To run your application, you can select between Cloud Foundry or one of your Kubernetes clusters running on IBM Cloud. 

After this selection a Toolchain will be created which integrates your Mendix Project within the Mendix Platform with your IBM Cloud environment. When using the Mendix modeler you now can use the 1 click deployment feature, to trigger a new version for the Toolchain to deploy. 

<!-- Related links section: still REQUIRED but moved to toc file (in your same folder).  Edit there.
-->