---

copyright:

  years:  2018

lastupdated: "2018-06-13"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with <service_short_name>
{: #gettingstarted}
<!-- Provide an appropriate ID above -->

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->


With <service_name>, you can connect a Rainbow user to an IBM Watson Assistant
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

To integrate your app with the service, complete these steps:

1. Sign into [Rainbow API Hub](http://hub.openrainbow.com/){: new_window} or [Register](https://www.openrainbow.com/subscribe_btm/){: new_window} for a Rainbow account

1. Register your Rainbow account as developer

 ![Register your developer account](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/01-register-developer-account_84f77837-56b7-4aba-a0c3-0a31a833bada.png)

1. Select **applications** entry in the left panel

 ![Developer Dashboard](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/02-dashboard-developer_107a58f3-e31e-4c05-9654-06c27dcf01bd.png)

1. Click on **Create Application** button and enter the new application informations

 ![Application button](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/03-create-application_9fa832ff-b551-4e96-9d52-36ef61c2d5dd.png)

 ![Create a new application](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/04-create-a-new-application_f4fe586f-c59f-48d5-b6c8-676047de4a97.png)

1. Once created You new application appear into your applications bashboard. Click on **Keys** button in order to retrieve your *Application ID* and the associated *Secret Key*, both informations are necessary for registering your bot.

 ![Open keys](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/05-open-keys_2441194a-ed2e-4c63-bbc7-b0f1e34910b6.png)

 ![Key details](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/06-key-details_13385af5-abc7-48ce-b416-eaf94c0d5765.png)

1. Create an additional Rainbow user account in order to converse with the Watson Assistant

1. Under IBM Catalog create or reuse an existing Watson Assistant service.

1. If necessary, download and install the [IBM Cloud Command Line Interface](https://console.bluemix.net/docs/starters/install_cli.html){: new_window}

- Change the API Endpoint
	```bash
	bluemix api https://api.ng.bluemix.net
	```
	{: pre}

- And login
	```bash
	bluemix login
	```
	{: pre}

1. Log into IBM Cloud Console and create a Rainbow Application Service

   - Click 'Catalog' at the top of the screen
   - Enter 'Rainbow'

    ![Rainbow app from IBM Cloud catalog](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/07-catalog-search-rainbow_51a3aecd-ff8d-46e1-8b25-31cfd1f6ef82.png)

1. After application creation, give a service name, and enter your **Login Email**, **Password**, **Application ID** and **Secret Key**, if you want to target our Sandbox platform instead of the production platform, simply enter *"sandbox"* into **Target Platform**

1. Locally, clone our sample application:

    ```bash
    git clone -b bluemix-rainbow-quickstart https://github.com/Rainbow-CPaaS/StarterKit-SDKNodeJSWatson.git
	````
    {: pre}

1. Deploy the application using the command line tools:

   ```bash
   bluemix app push <Your App Name>
   ```
   {: pre}

1. In the IBM Cloud Dashboard, you are able to see <Your App Name>, click on your Rainbow Service under 'Cloud Foundry Services',
   then click the 'Create connection +' button. Connect it to your new <Your App Name> application.
   Do the same with your Watson Assistant service.

	{: screen}



<!-- Related links section: still REQUIRED but moved to toc file (in your same folder).  Edit there.
-->
![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/07-catalog-search-rainbow_51a3aecd-ff8d-46e1-8b25-31cfd1f6ef82.png)
![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/06-key-details_13385af5-abc7-48ce-b416-eaf94c0d5765.png)
![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/05-open-keys_2441194a-ed2e-4c63-bbc7-b0f1e34910b6.png)
![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/04-create-a-new-application_f4fe586f-c59f-48d5-b6c8-676047de4a97.png)
![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/03-create-application_9fa832ff-b551-4e96-9d52-36ef61c2d5dd.png)
![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/02-dashboard-developer_107a58f3-e31e-4c05-9654-06c27dcf01bd.png)
![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/product_documentation_image_/01-register-developer-account_84f77837-56b7-4aba-a0c3-0a31a833bada.png)