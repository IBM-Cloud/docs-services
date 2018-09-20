---

copyright:

  years:  2017

lastupdated: "2018-09-19"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Passport
{: #gettingstarted}

Passport is a modern take on identity access management. Passport delivers authentication, authorization, SSO and security to your IBM Cloud application with modern REST APIs. Focus on your core business, let Passport handle your users.

The Passport APIs can be integrated into any platform. Our REST APIs are well documented and we have also provided native bindings in C#, Java, Node, Ruby, JavaScript, PHP and Python. If we're missing an SDK for the library you'll be integrating Passport with let us know and we'll build it for you.
{:shortdesc}

## On your mark, get set, go!
This guide will have you up and running in 20 minutes or less. Before you can start calling Passport APIs in your IBM Cloud application complete the following steps.

1. Find [Passport Service](https://console.ng.bluemix.net/catalog/services/passport/){:new_window} in the IBM Cloud Catalog
2. Make a note of the **Service name** field, and change the name if you'd like.
3. If you don't already have a Passport license, register at [www.inversoft.com](https://www.inversoft.com "Inversoft"){:new_window} and complete the [IBM Cloud Integration](https://www.inversoft.com/docs/passport/1.x/tech/tutorials/bluemix-integration "IBM Cloud Integration Tutorial"){:new_window} tutorial. That tutorial will cover all steps provided here as well. 
4. Complete the Passport Credentials section on the Passport service page. These values will be available to your application at runtime in order to connect and authenticate to the Paspport API.
  * API Key
  * Passport Backend URL

5. Complete the configuration by Connecting the Passport service to your application. On the left side of the page you'll see a 'Connect to:' selector, select the desired application, and then click on 'Create'. 

6. Add the **Service name** you made note of in Step 2 and the **Application Id** you made note of during Step 3 as User defined Runtime Environment Variables. For example:
  * `passport_application_id = 4ed5eb32-0a97-40eb-a6d7-cca1f9fa3a0c`
  * `passport_service_name = Passport-vz`

7. In your application, you can then access those values, make API calls, or utilize the Node.js Passport client.

  ```
	const services = JSON.parse(process.env.VCAP_SERVICES);
	let passport = null;
	const user_provided = services["user-provided"];
	// User defined Environment Variable : passport_service_name
	const serviceName = process.env.passport_service_name;
	for (let i=0; i < user_provided.length; i++) {
	  if (user_provided[i].name === serviceName) {
	    passport = user_provided[i];
	  }
	}
	 
	let apiKey = passport.credentials.api_key;
	let backendURL = passport.credentials.passport_backend_url;
	
	// User defined Environment Variable : passport_application_id
	let applicationid = process.env.passport_application_id;
  ```
  {: codeblock}

<!-- separate to test-->

  ```
	const PassportClient = require('passport-node-client');
	        
	// Construct the client and start making API calls
	let passportClient = new PassportClient(apiKey, backendURL);
	
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
  
<!-- Separate to test-->  

<!-- Related links are now in the toc file:
# Related Links
{: #rellinks notoc}

## Tutorials and Samples
{: #samples}

* [Bluemix Integration Tutorial](https://www.inversoft.com/docs/passport/1.x/tech/tutorials/bluemix-integration){:new_window}
* [ToDo Application demonstrating Passport APIs Sample Application](https://github.com/inversoft/passport-bluemix-example){:new_window}
  * React front end making direct API calls to Passport and storing the JWT (access token)
  * Node backend to a MySQL database using the JWT from the front end to verify identity.

## SDK
{: #sdk}

* [Passport Client Libraries](https://www.inversoft.com/docs/passport/1.x/tech/client-libraries/){:new_window}

## API Reference
{: #api}

* [REST APIs](https://www.inversoft.com/docs/passport/1.x/tech/apis/){:new_window}

## Related Links
{: #general}

* [Plans and Pricing](https://www.inversoft.com/try-passport){:new_window}
* [Technical Documentation](https://www.inversoft.com/docs/passport/1.x/tech/){:new_window}
-->