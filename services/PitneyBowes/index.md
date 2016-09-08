{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}


# Getting Started with Pitney Bowes APIs
{: #gettingstarted}

*Last updated: 08 September 2016*
{: .last-updated}

Pitney Bowes APIs allow any developer to access enterprise-class solutions for applications ranging from business intelligence to customer engagement and commerce. These solutions are used by leading companies in industries such as banking, insurance and retail, enabling end users to make the best decisions and achieve the best business outcomes. Now available to developers via modern REST APIs, developers in any size organization can access these class-leading tools and datasets, rapidly deploying and scaling solutions.
{:shortdesc}

The APIs are broadly categorized into following:
* Identify - Break down names and addresses, correct and validate your data, then add insight about your customers.
* Locate – Highly accurate and comprehensive datasets that add context to locations. Mix-in and mash-up geodata to allow you to unlock deeper insight, orchestrate workflows or engage more effectively customers.
* Communicate – Enable multi-channel communications with clients or prospects (Coming Soon)
* Ship - Add feature-rich USPS shipping capabilities to eCommerce or IoT applications - it's shipping made simple.
*	Pay - Charge accurate import duty & taxes at checkout and offer a total landed cost to your international customers.


##Before you begin

Ensure that you have the Cloud Foundry CLI installed on your computer. The CLI is available here: https://github.com/cloudfoundry/cli#downloads. After the CLI is installed, you'll be able to use the cf command from your command line interface.

## Setting up Pitney Bowes APIs

To add APIs from Pitney Bowes service to your Bluemix application, follow these steps:

1. Set up the Bluemix API endpoint:
  ```
  cf api https://api.ng.bluemix.net
  ```
  {: codeblock}
2. Log in to Bluemix with your Bluemix credentials:
  ```
  cf login
  ```
  {: codeblock}
3. Choose your organization and space, and create a service instance in your selected space. For example, using `pitneybowes free` as the service and `mypitneybowes01` as the service instance name:
  ```
  cf create-service PitneyBowes-APIs Free mypitneybowes01
  ```
  {: codeblock}

 
•	 Bind your Pitney Bowes APIs instance to your application, for example:

cf bind-service MyApp mypitneybowes01

where 'MyApp' is your application and ‘mypitneybowes01’ is your service instance.
•	 Optionally, to show the service is bound to your application, use the cf services command. 
•	After Pitney Bowes APIs are bound to your application, the specific configuration of your Pitney Bowes APIs will appear in your environment variable. To list the details, use the cf env command followed by your application name, for example:
           cf env MyApp
           where 'MyApp' is your application.
 
The credentials block provides everything you need to use the APIs from Pitney Bowes.
•	apiKey - your key for accessing the Pitney Bowes API
•	apiSecret - the secret for accessing the Pitney Bowes API
To get started using the API to transcode your media files, please see the API QuickStart and the API Specification.


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


Getting Started with Pitney Bowes APIs

The APIs are broadly categorized into following:
•	Identify - Break down names and addresses, correct and validate your data, then add insight about your customers.  
•	Locate – Highly accurate and comprehensive datasets that add context to locations. Mix-in and mash-up geodata to allow you to unlock deeper insight, orchestrate workflows or engage more effectively customers.
•	Communicate – Enable multi-channel communications with clients or prospects (Coming Soon)
•	Ship - Add feature-rich USPS shipping capabilities to eCommerce or IoT applications - it's shipping made simple.
•	Pay - Charge accurate import duty & taxes at checkout and offer a total landed cost to your international customers.

Setting up Pitney Bowes APIs
To add the APIs using the command line, you need the Cloud Foundry CLI installed on your computer. Get it from https://github.com/cloudfoundry/cli#downloads. Once it’s installed, you'll be able to use the cf command from your command line interface.
To add APIs from Pitney Bowes service to your Bluemix application, follow these steps:
•	 Set up the Bluemix API endpoint:

cf api https://api.ng.bluemix.net
•	 Then log in to Bluemix with your Bluemix credentials:

 cf login
 
•	 Choose your organization and space, and you are ready to add the APIs from Pitney Bowes service. 
•	 Now create a service instance in your selected space, for example:

cf create-service PitneyBowes-APIs Free mypitneybowes01

where ‘pitneybowes free’ is the service and 'mypitneybowes01' is the service instance name. 
•	 Bind your Pitney Bowes APIs instance to your application, for example:

cf bind-service MyApp mypitneybowes01

where 'MyApp' is your application and ‘mypitneybowes01’ is your service instance.
•	 Optionally, to show the service is bound to your application, use the cf services command. 
•	After Pitney Bowes APIs are bound to your application, the specific configuration of your Pitney Bowes APIs will appear in your environment variable. To list the details, use the cf env command followed by your application name, for example:
           cf env MyApp
           where 'MyApp' is your application.
 
The credentials block provides everything you need to use the APIs from Pitney Bowes.
•	apiKey - your key for accessing the Pitney Bowes API
•	apiSecret - the secret for accessing the Pitney Bowes API
To get started using the API to transcode your media files, please see the API QuickStart and the API Specification.
 


