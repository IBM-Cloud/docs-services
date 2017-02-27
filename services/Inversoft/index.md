---

copyright:

  years:  2016, 2017

lastupdated: "2017-02-11"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with Passport
{: #gettingstarted}
<!-- Provide an appropriate ID above -->

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->

Passport is a modern taken on identity access management. Passport delivers authentication, authorization, SSO and security to your Bluemix application with modern REST APIs. Focus on your core business, let Passport handle your users.
{:shortdesc}

The Passport APIs can be integrated into any platform. Our REST APIs are well documented and we have also provided native bindings in C#, Java, Node, PHP and Python. If we're missing an SDK for the library you'll be integrating Passport with let us know and we'll build it for you.
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

To integrate the Passport service into your application, complete the following:

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

1. Find Passport in the Bluemix Catalog
  * Customize the sevice name field if necessary.
2. Make a note of the Service name field, and change the name if you'd like. Make a note of this value. 
2. If you don't already have a Passport license, register at [www.inversoft.com](https://www.inversoft.com "Inversoft") and complete the [Bluemix Integration](https://www.inversoft.com/docs/passport/1.x/tech/tutorials/bluemix-integration "Bluemix Integration Tutorial") tutorial. That tutorial will cover all steps provided here as well. 
3. Complete the Passport Credentials section of the service. These values will be available to your application at runtime in order to connect and authenticate to the Paspport API.
  * API Key
  * Passport Backend URL
  * Passport Frontend URL

3. Complete the configuration by Connecting the Passport service to your application. On the left side of the page you'll see a 'Connect to:' selector, select the desired application, and then click on 'Create'. 

4. In your application you may then access those values make API calls or utilize the Node.js Passport client.

	```
          const appenv = JSON.parse(process.env.VCAP_APPLICATION);
          const services = appenv.services;

          // Look up the service definition by name as specified in Step 2 above.
         let passport = null;
         const user_provided = services["user-provided"];
         for (let i=0; i < user_provided.length; i++) {
           if (user_provided[i].name === 'Passport-vz') {
             passport = user_provided[i];
           }
         }
 
         let apiKey = passport.credentials.api_key;
         let applicationId = passport.credentials.application_id;
         let backendURL = passport.credentials.passport_backend_url;
         let frontendURL = passport.credentials.passport_frontend_url;

         // User defined Environment Variable for the Application Id, this will be specific for each Bluemix Application
         let applicationid = process.env.passport_application_id;
	```
	{: codeblock}

	```
        // Use the Inversoft Passport Node Client if running in Node.
        // If you need to compile for the browser this client will not currently work as it is written using ES6 features.
        // Require the passport-node-client
        // https://www.npmjs.com/package/passport-node-client 
        // https://github.com/inversoft/passport-node-client
        const PassportClient = require('passport-node-client');
        
        // Construct the client and start making API calls
	let passportClient = new PassportCLient(apiKey, backendURL);

        // Retrieve the JWT public key used to verify JWT signatures for our application
        passportClient.retrieveJwtPublicKeys(applicationId)
        .then((response) => {
          // Store off this public key to use when verifying JWT signatures
          const publicKey = response.successResponse.publicKey;
        }).catch((response) => {
          console.error('Failed to retrieve the JWT Public Key. Verify your Passport Configuration');
        });
        	
	```
        {: codeblock}




<!-- Related links section: REQUIRED.
Related links display in the upper right of the getting started page. 
Ensure that you retain the lowercase anchor IDs (eg. {: #rellinks}) as shown in this template. These are used as IDs during transform and the doc framework keys off the IDs for display. 
The headings coded here are not actually used. The doc framework provides the correct headings. 
Also ensure that the related links stay in position at the end of this file or the doc framework will not display them properly.
Use {:new_window} for external links to open a new window.-->
<!-- Please delete all comments within the related links section to avoid breaking the build. Thanks. -->

# Related Links
{: #rellinks notoc}

## Tutorials and Samples
{: #samples}

* [Getting Started with Passport on IBM Bluemix](https://www.ibm.com/blogs/bluemix/_pending_blog_publish_)
* [Bluemix Integration Tutorial](https://www.inversoft.com/docs/passport/1.x/tech/tutorials/bluemix-integration)
* [ToDo Application demonstrating Passport APIs Sample Application](https://github.com/inversoft/passport-bluemix-example)
  * React front end making direct API calls to Passport and storing the JWT (access token)
  * Node backend to a MySQL database using the JWT from the front end to verify identity.

<!-- Recommended external links to your top three devWorks articles and sample applications. NOTE: sample apps should be in node and java at a minimum. Link text should be: <sample_name> sample or developerworks: <article_name>. To confirm the available articles for your service, go to http://www.ibm.com/developerworks/views/global/libraryview.jsp?show_abstract=falsecontentarea_by=All+Zonesproduct_by=-1topic_by=BlueMixindustry_by=-1type_by=All+Typesibm-search=Search and select your service from the product drop-down menu -->

* [link text](URL){:new_window}

## SDK
{: #sdk}

<!-- Links to SDK download and SDK Developer Guide -->

* [Java](https://www.inversoft.com/docs/passport/1.x/tech/client-libraries/java){:new_window}
* [C#](https://www.inversoft.com/docs/passport/1.x/tech/client-libraries/csharp){:new_window}
* [Node.js](https://www.inversoft.com/docs/passport/1.x/tech/client-libraries/node){:new_window}
* [PHP](https://www.inversoft.com/docs/passport/1.x/tech/client-libraries/php){:new_window}

## API Reference
{: #api}

<!-- External links to the landing page of each generated doc for the APIs that are supported by your service. Use only the type of API as the link text (Java, JavaScript, REST, Objective-C) -->

* [REST APIs](https://www.inversoft.com/docs/passport/1.x/tech/apis/){:new_window}

## Compatible Runtimes
{: #buildpacks}

<!-- MAY BE REMOVING THIS: Peer links to the Getting Started page of each runtime that is supported by your service. Use only the name of the runtime as the link text (Node.js, Liberty for Java, Ruby on Rails, Ruby Sinatra) -->

* [link text](URL)

## Related Links
{: #general}

<!-- Include a link to your full product documentation, pricing sheet, IBM Bluemix prerequisites -->
<!-- NOTE: Remove these comments when using this template. Otherwise the comment will break the build! Thanks. -->

* [Plans and Pricing](https://www.inversoft.com/try-passport){:new_window}
* [1.x Technical Documentation](https://www.inversoft.com/docs/passport/1.x/tech/){:new_window}
