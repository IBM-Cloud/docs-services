# Getting Started with the flowthings.io service for Bluemix

[flowthings.io](https://flowthings.io) is a cloud based solution for real time data collection, complex event processing, and data delivery. The service is built from the ground up to make it extremely easy to use and easy to integrate with almost any software or device.

## Binding the flowthings.io service in Bluemix

You can bind to the flowthings.io service via the Bluemix web console.

From the [bluemix dashboard](https://console.ng.bluemix.net/), go to "services" and choose to add a service. Select flowthings.io from the presented list, and then fill out the “Add Service” form to create a binding to a specific space and application.

This documentation does not cover the full range of options for managing applications and service bindings in Bluemix. You should refer to the Bluemix documentation regarding questions about Bluemix itself.

## Configure flowthings.io for your application

Once Flowthings has been bound to the application, the credentials will be in your VCAP_SERVICES environmental variable as follows:

```json
{
   "flowthings": [
      {
         "name": "flowthings",
         "label": "flowthings",
         "plan": "free",
         "credentials": {
            "account": "<account_name>",
            "token": "<account_token>"
         }
      }
   ]
}
```

Using the `account` and `token` given in the credentials, you can communicate between your application to flowthings.io via any of the protocols supported by flowthings.io or with one of [various libraries](https://flowthings.io/developers/libraries).

If you're using the flowthings.io node.js library, once the library is installed (typically via your `package.json` file), you can connect as follows:

```javascript
var flowthings = require('flowthings')

var flowthingsAccount = config['flowthings'][0].credentials.account;
var flowthingsToken = config['flowthings'][0].credentials.token;

var creds = {account: flowthingsAccount, token: flowthingsToken};
var api = flowthings.API(creds);
```

You can see the documentation for the [node.js library](https://github.com/flowthings/node-client/blob/master/README.md) for more.

## Use flowthings.io

Once you have your credentials configured for your library of choice, you're ready to use the service to collect, process, and deliver realtime streams of agile intelligence to and from your application.

To learn more about the functionalities and services provided by flowthings.io, check out the [documentation](https://flowthings.io/docs/getting-started) and [tutorials](https://flowthings.io/developers/tutorials).

