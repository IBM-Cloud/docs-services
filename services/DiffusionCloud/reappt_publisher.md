{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# Create a Node.js publisher
{: #reappt_publisher}

*Last updated: 13 February 2017*
{: .last-updated}


Create a Node.js™ app hosted in Bluemix that is bound to Diffusion Cloud and uses it to publish data through topics.
{:shortdesc}


To complete this example, you need [a Diffusion Cloud service](https://console.ng.bluemix.net/catalog/services/diffusion-cloud-from-push-technology/) and a Bluemix web application that uses [SDK for Node.js](https://console.ng.bluemix.net/catalog/starters/sdk-for-nodejs/).  


This example steps through creating an SDK for Node.js app that uses a bound Diffusion Cloud service to publish data. The full code example is provided after the steps.


1. Use the Bluemix user interface to bind your Diffusion Cloud service to your Node.js app.
   The credentials that are created for the binding use a principal that has the `CLIENT`, `TOPIC_CONTROL`, and `CLIENT_CONTROL` roles. In the Diffusion Cloud Dashboard, you can modify the roles that the principal has, but do not delete the principal or change its password.

2. Select Start Coding from the left sidebar.

3. Follow the instructions on the Start Coding page to get the app code.

4. Edit the `package.json` file to include the `diffusion` client library as a dependency:
   ```
   "dependencies": {
        "express": "4.13.x",
        "cfenv": "1.0.x",
        "diffusion": "5.8.0"
   },
   ```

5. Edit the `app.js` file:
   *  Include the JavaScript library.
     
     ```
      var diffusion = require('diffusion');
      ```
      {: codeblock}
   *  Include the JavaScript library.

      ```
      var vcap_services = {};
      try {
          vcap_services = JSON.parse(process.env.VCAP_SERVICES);
      }
      catch (e) {
	     console.log('Cannot parse VCAP_SERVICES. Check the binding is present.');
	     process.exit(1);
      }
      ```
      {: codeblock}
   *  Inside the `app.listen` method, use the options from the bindings credentials to connect to Reappt.
 
      ```
      var option = vcap_services['push-reappt'][0].credentials;

      diffusion.connect(options).then(function(session) {
         console.log('Connected!');

      });
      ```  
      {: codeblock}    
   *  Once the client is connected to Reappt, use the session to create a topic and update it every second with an incrementing counter.
      ```
      var count = 0;
        
      // Create a topic with a default value of 0. 
      session.topics.add('foo/counter', count);
  
      // Start updating the topic every second
      setInterval(function() {
          session.topics.update('foo/counter', ++count);
      }, 1000);
      ```
      {: codeblock}
5. Follow the instructions on the Start Coding page to upload your edited `app.js` file.

6. Start your app.



# Full example 

```
var cfenv = require('cfenv');
var diffusion = require('diffusion');

var vcap_services = {};
try {
	vcap_services = JSON.parse(process.env.VCAP_SERVICES);
}
catch (e) {
	console.log('Cannot parse VCAP_SERVICES. Check the binding is present.');
	process.exit(1);
}

var app = express();
app.use(express.static(__dirname + '/public'));

var appEnv = cfenv.getAppEnv();

app.listen(appEnv.port, '0.0.0.0', function() {

    console.log("Server starting on " + appEnv.url);

    var option = vcap_services['push-reappt'][0].credentials;

    diffusion.connect(options).then(function(session) {
        console.log('Connected!');

        var count = 0;
        
        // Create a topic with a default value of 0. 
        session.topics.add('foo/counter', count);
  
        // Start updating the topic every second
        setInterval(function() {
            session.topics.update('foo/counter', ++count);
        }, 1000);
    });
});
```
{: codeblock}




## Start publishing
{: #start_publishing}

* [Start publishing in JavaScript](http://docs.pushtechnology.com/cloud/latest/manual/html/developerguide/apis/javascript/getting_started_publisher.html){:new_window}
* [Start publishing in Android](http://docs.pushtechnology.com/cloud/latest/manual/html/developerguide/apis/android/getting_started_publisher.html){:new_window}
* [Start publishing in Apple](http://docs.pushtechnology.com/cloud/latest/manual/html/developerguide/apis/apple/getting_started_publisher.html){:new_window}
* [Start publishing in Java](http://docs.pushtechnology.com/cloud/latest/manual/html/developerguide/apis/java/getting_started_publisher.html){:new_window}
* [Start publishing in .NET](http://docs.pushtechnology.com/cloud/latest/manual/html/developerguide/apis/dotnet/getting_started_publisher.html){:new_window}
* [Start publishing in C](http://docs.pushtechnology.com/cloud/latest/manual/html/developerguide/apis/c/getting_started_publisher.html){:new_window}

 
