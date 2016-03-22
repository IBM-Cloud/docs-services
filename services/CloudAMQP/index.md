
# Getting started with CloudAMQP

*Last updated: 23 April 2016*

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->

CloudAMQP on Bluemix are RabbitMQ servers hosted in the cloud. 
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



<!-- Include a sentence to briefly introduce the steps. Examples: -->

Complete these steps to get started with the CloudAMQP service:

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->
 
If you are new to RabbitMQ, we recommend you read the guide [RabbitMQ for beginners before continuing](https://www.cloudamqp.com/blog/2015-05-18-part1-rabbitmq-for-beginners-what-is-rabbitmq.html?cm_mc_uid=22273308531414543392018&cm_mc_sid_50200000=1458671296).

###Steps to integrate app with the service.

All AMQP client libraries work with CloudAMQP and there are AMQP client libraries for almost every platform. Sample code, links to recommended libraries and further information about the client libraries can be found in [the CloudAMQP documentation](https://www.cloudamqp.com/docs/index.html). 

1.  Add the client library to your dependencies file. The library will be downloaded automatically when you deploy your app. CloudAMQP recommended client libraries for different languages can be found here:      [Ruby](https://www.cloudamqp.com/docs/ruby.html), [Python](https://www.cloudamqp.com/docs/python.html), [Celery](https://www.cloudamqp.com/docs/celery.html), [node.js](https://www.cloudamqp.com/docs/nodejs.html), [PHP](https://www.cloudamqp.com/docs/php.html), [Java](https://www.cloudamqp.com/docs/java.html), [Clojure](https://www.cloudamqp.com/docs/clojure.html), [Go](https://www.cloudamqp.com/docs/go.html), [Android](https://www.cloudamqp.com/docs/android.html), [.NET](https://www.cloudamqp.com/docs/dotnet.html), [Perl](https://www.cloudamqp.com/docs/perl.html) and [C](https://www.cloudamqp.com/docs/c.html). For example, in Ruby, open the Gemfile and add gem ‘bunny’. 
    
    ```
    gem 'bunny'
    ```
* Copy code from the the same language-specific link as above. For example, in Ruby: 


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
<!-- Recommended external links to your top three devWorks articles and sample applications. 	Link text should be: <sample_name> sample or developerworks: <article_name>. To confirm the available articles for your service, go to http://www.ibm.com/developerworks/views/global/libraryview.jsp?show_abstract=falsecontentarea_by=All+Zonesproduct_by=-1topic_by=BlueMixindustry_by=-1type_by=All+Typesibm-search=Search and select your service from the product drop-down menu -->
* [link text](URL){:new_window}
## SDK
{: #sdk}
<!-- Links to SDK download and SDK Developer Guide -->
* [link text](URL){:new_window}
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

