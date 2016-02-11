{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

<!-- This template is for getting started with a third-party Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  Marketing material about the service is included in the catalog. Don't use the getting started to include more details about
the service. Instead, include short getting started instructions, plus a short code snippet that can show an example of the coding used with your service to give the developer a view of the coding for the service. -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with <service_short_name>
<!-- Insert your short service name into topic title above -->
{: #gettingstartedtemplate}
<!-- Provide and appropriate ID above -->
*Last updated: nn month yyyy*

<!-- Short description: REQUIRED
The short description section should include one to three sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->

IBM Single Sign On is a policy-based authentication service for Bluemix. With Single Sign On, you can easily embed single sign-on capability in Node.js or Liberty for Java apps. -OR-
With IBM IoT Real-Time Insights on Bluemix, you can perform analytics on real-time data from your Internet of Things devices, and gain insights about their health and the overall state of your operations.  -OR-
Use IBM BigInsights for Apache Hadoop for Bluemix to provision enterprise-scale, multi-node big data clusters on the IBM SoftLayer cloud. After they are provisioned, you can manage and access these clusters from the BigInsights service.
{: shortdesc}

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
```
{: codeblock}

3. Step 3

```
my command -and -options
```
{: codeblock}

4. Step 4
```
This is a bunch of output from
	a command or program I ran
		and it can run lots of lines
```
{: screen}

<!-- About service_name_short section: OPTIONAL
This is an optional overview section if needed for your service. Delete this section if not using. -->

## About <service_name_short>
<!-- Insert your short service name into topic title above -->
{: #about_servicename}

<!-- The short description section should include a sentence introducing the concepts. For example: -->
With the {{site.data.keyword.hadoop}} service, you can access most of the capabilities of IBM BigInsights Version 4.0, on the cloud. 
{:shortdesc}

### Concept title
{: #servicename_concept}


<!-- Additional task section: OPTIONAL
If you have additional tasks like configuring, managing, etc. you can add on or more task sections for your service. Use a task title with gerun such as "Configuring x", "Administering y", "Managing z".
Delete this section if not using. -->

# Task title with gerund
<!-- for example, Uploading your data -->
{: #servicename_task}
*Last updated: nn month yyyy*

<!-- The short description section should include a sentence describing why this task is needed. For search engine optimization, include the service long name and "Bluemix". For example: -->

Before you can start processing your {{site.data.keyword.Bluemix_notm}} application data with {{site.data.keyword.hadoop}}, you must first upload it to the {{site.data.keyword.hadoopst}} Hadoop Distributed File System (HDFS) file structure. 
{:shortdesc}

<!-- Include a sentence to briefly introduce the steps/subtopics. Example: -->
Complete the following tasks to upload your data to the HDFS environment with the webHDFS REST API.

## Sub task title with gerund
<!-- for example, Finding the password -->
{: #servicename_subtask}

<!-- Include a sentence describing why this task is needed.  For example: -->
To access the HDFS file system, you must connect as the `biblumix` user, so that you can access the `/user/biblumix` directory in HDFS.

<!-- Include a sentence to briefly introduce the steps. For example:-->

To find the `biblumix` user password, follow these steps:

<!-- Use ordered list markup for the step section. Include code examples as needed. -->

1. Step 1
**Tip:** blah blah

2. Step 2. For example input:
```
copyable code
```
{: codeblock}

3. Step 3. For example output:
```
displayed info
```
{: screen}

<!-- Related links section: REQUIRED.
Related links display in the upper right of the getting started page. 
Ensure that you retain the lowercase headings as shown in this template. These are converted to IDs during transform and the doc framework keys off the IDs for display. The doc framework provides the correct headings. 
Also ensure that the related links stay in position at the end of this file.-->
<!-- Please delete all comments within the related links section to avoid breaking the build. Thanks. -->

# rellinks
## general 
<!-- Include a link to your full product documentation and other sites as needed. -->
<!-- NOTE: Remove these comments when using this template. Otherwise the comment will break the build! Thanks. -->
* [link text](URL)
* [link text](URL)
* [link text](URL)
