---

copyright:

  years:  2017-2018

lastupdated: "2018-09-19"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with FusionAuth
{: #gettingstarted}

FusionAuth is a modern take on identity access management. FusionAuth delivers authentication, authorization, SSO and security to your IBM Cloud application with modern REST APIs. Focus on your core business, let FusionAuth handle your users.

The FusionAuth APIs can be integrated into any platform. Our REST APIs are well documented and we have also provided native bindings in C#, Java, Node, Ruby, JavaScript, PHP and Python. If we're missing an SDK for the library you'll be integrating FusionAuth with let us know and we'll build it for you.
{:shortdesc}

## On your mark, get set, go!
This guide will have you up and running in 20 minutes or less. Before you can start calling FusionAuth APIs in your IBM Cloud application complete the following steps.

1. Find [FusionAuth Service](https://console.ng.bluemix.net/catalog/services/fusionauth/){:new_window} in the IBM Cloud Catalog
2. Make a note of the **Service name** field, and change the name if you'd like.
3. Install FusionAuth by one of the supported methods. See [Getting Started](https://fusionauth.io/docs/v1/tech/getting-started/) 
4. Complete the FusionAuth Credentials section on the FusionAuth service page. These values will be available to your application at runtime in order to connect and authenticate to the FusionAuth API.
  * API Key
  * FusionAuth URL
5. Complete the configuration by Connecting the FusionAuth service to your application. On the left side of the page you'll see a 'Connect to:' selector, select the desired application, and then click on 'Create'. 
6. Add the **Service name** you made note of in Step 2 and the **Application Id** you made note of during Step 3 as User defined Runtime Environment Variables. For example:
  * `fusionauth_application_id = 4ed5eb32-0a97-40eb-a6d7-cca1f9fa3a0c`
  * `fusionauth_service_name = FusionAuth-vz`

7. In your application, you can then access those values, make API calls, or utilize the Node.js FusionAuth client.

  ```
	const services = JSON.parse(process.env.VCAP_SERVICES);
	let fusionauth = null;
	const user_provided = services["user-provided"];
	// User defined Environment Variable : fusionauth_service_name
	const serviceName = process.env.fusionauth_service_name;
	for (let i=0; i < user_provided.length; i++) {
	  if (user_provided[i].name === serviceName) {
	    fusionauth = user_provided[i];
	  }
	}
	 
	let apiKey = fusionauth.credentials.api_key;
	let serviceURL = fusionauth.credentials.fusionauth_backend_url;
	
	// User defined Environment Variable : fusionauth_application_id
	let applicationid = process.env.fusionauth_application_id;
  ```
  {: codeblock}

<!-- separate to test-->

  ```
	const FusionAuthClient = require('fusionauth-node-client');
	        
	// Construct the client and start making API calls
	let fusionauthClient = new FusionAuthClient(apiKey, serviceURL);
	
	// Retrieve the JWT public key used to verify JWT signatures for our application
	fusionauthClient.retrieveJwtPublicKeys(applicationId)
	.then((response) => {
	  // Store off this public key to use when verifying JWT signatures
	  const publicKey = response.successResponse.publicKey;
	}).catch((response) => {
	  console.error('Failed to retrieve the JWT Public Key. Verify your FusionAuth Configuration');
	});      	
  ```
  {: codeblock}
  
<!-- Separate to test-->  

<!-- Related links are now in the toc file:
# Related Links
{: #rellinks notoc}

## SDK
{: #sdk}

* [FusionAuth Client Libraries](https://fusionauth.io/docs/v1/tech/client-libraries/){:new_window}

## API Reference
{: #api}

* [REST APIs](https://fusionauth.io/docs/v1/tech/apis/){:new_window}

## Related Links
{: #general}

* [Technical Documentation](https://fusionauth.io/docs/v1/tech/){:new_window}
-->
