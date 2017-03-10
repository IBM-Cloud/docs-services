---

copyright:

  years: 2017

lastupdated: "2017-03-10"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with PagerDuty
{: #gettingstarted}

PagerDuty is TODO
{:shortdesc}


## Steps to integrate your app with PagerDuty

### In PagerDuty

1. [Create a free account](https://signup.pagerduty.com/){:new_window} if you haven't already created an account.

2. From the **Configuration** menu, select **Services**.

3. On your Services page:

    - If you are creating a new service for your integration, click **+Add New Service**.

    - If you are adding your integration to an existing service, click the name of the service you want to add the integration to. Then click the **Integrations** tab and click the **+New Integration** button.

4. Select **IBM Bluemix** from the **Integration Type** menu and enter an **Integration Name**.

5. Click the **Add Service** or **Add Integration** button to save your new integration. You will be redirected to the Integrations page for your service.

6. Copy the **Integration Key** for your new integration.

## Creating an OpenWhisk action

1. Copy this code.

```
// This action will trigger or resolve an incident within PagerDuty
//
// The params object passed to the action should be a payload formatted for the PagerDuty Events API
// The params object must contain a "service_key" and "description". The "event_type" will default to "trigger".
//
// https://v2.developer.pagerduty.com/docs/trigger-events

var request = require('request');

function main(params) {
	// Check for required params
	if (!params.service_key || !params.description) { throw 'params must include service_key and description'; }
	if (!params.event_type) { params.event_type = 'trigger'; }

	console.log(`Params: ${JSON.stringify(params)}`);

	// Set request options
	var options = {
		url: 'https://events.pagerduty.com/generic/2010-04-15/create_event.json',
		method: 'POST',
		json: true,
		body: params
	};

	// Make POST request
	return new Promise(function(resolve, reject) {
		request(options, function(error, response, body) {
			if (error) {
				reject(error);
			}
			else {
				resolve(body);
			}
		});
	});
}
```
{:codeblock}

### In Your Browser

1. Go to your [OpenWhisk Editor](https://console.ng.bluemix.net/openwhisk/editor){:new_window}.

2. Click on **Create an Action**.

3. Paste the code you copied above into the editor.

4. Click on **Make It Live**.

### Using OpenWhisk CLI

1. Paste the code you copied above into a new JavaScript file. In this example we named the file `pagerduty.js`.

2. Run the command below replacing `pagerduty` with your preferred action name and `pagerduty.js` with the filename of your JavaScript file.

```
wsk action create pagerduty pagerduty.js
```
{:pre}

## Triggering an incident in PagerDuty

1. Invoke the PagerDuty action you created

2. Pass the action parameters formatted for the PagerDuty [Events API](https://v2.developer.pagerduty.com/docs/trigger-events){:new_window}.

Here is an example where the `pagerduty` action is invoked using the OpenWhisk CLI but the action can also be invoked using OpenWhisk's event-driven triggers and rules.

```
wsk action invoke pagerduty --blocking --result --param event_type trigger --param description "Server is on fire" --param service_key bdb63026b4514cd7b143604f460cca30f
```
{:pre}

## Managing an incident in PagerDuty

1. Invoke the PagerDuty action being sure to update your `incident_key` parameter to match the `incident_key` for the incident you want to manage.

    - Acknowledge an incident:

    ```
    wsk action invoke pagerduty --blocking --result --param event_type acknowledge --param service_key bdb63026b4514cd7b143604f460cca30f --param incident_key 8e6cd11a23a34985b4a94fd556326132
    ```
    {:pre}

    - Resolve an incident:

    ```
    wsk action invoke pagerduty --blocking --result --param event_type resolve --param service_key bdb63026b4514cd7b143604f460cca30f --param incident_key 8e6cd11a23a34985b4a94fd556326132
    ```
    {:pre}


# Related Links
{: #rellinks notoc}

## Tutorials and Samples
{: #samples}


## API Reference
{: #api}

* [PagerDuty Developer Hub](https://v2.developer.pagerduty.com/)
* [API Reference](https://v2.developer.pagerduty.com/v2/page/api-reference)


## Related Links
{: #general}
