{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# Create a JavaScript/HTML subscriber
{: #reappt_subscriber}

*Last updated: 01 July 2016*
{: .last-updated}


Create a JavaScript client that connects to your Reappt service, subscribes to a topic and displays the value of the topic.
{:shortdesc}


To complete this example, you need a Reappt service and a user on that service that has the CLIENT role. 


This example steps through creating a subscribing client. The full code example is provided after the steps.


1. Create a template HTML file.
   ```
   <html>
     <head>
       <title>JavaScript example</title>    
     </head>
     <body>
       <div>
         <span>The value of foo/counter is: </span>
         <span id="update">Unknown</span>
       </div>
     </body>
   </html>
   ```
   {: codeblock}

2. Include the Reappt JavaScript library in the `head` section of your file.
   ```
   <html>
     <head>
       <title>JavaScript example</title>
       <script type="text/javascript" src="http://developer.reappt.io/clients/js/diffusion.js"></script>
     </head>
   </html>
   ```
   {: codeblock}

3. Create a connection from the page to Reappt. Add a `script` element to the `body` section of your file.
   ```
   <script type="text/javascript">
      diffusion.connect({
          // Edit this line to include the URL of your Reappt service
          host : 'service-name.reappt.io',
          
          // To connect anonymously you can leave out the following parameters
          principal : 'user',
          credentials : 'password'
      }).then(subscribeToTopic);
   </script>
   ```
   {: codeblock}

4. Edit the host parameter to be the name of your Reappt service.
   You can get the host name from the Reappt Dashboard.

5. Edit the principal and credentials parameters to be the username and password of a Reappt user with the CLIENT role.
   You can create a user in the system users table of the Reappt Dashboard.

6. Create a function that subscribes to a topic and receives data from it.
   ```
      function subscribeToTopic(session) {
          session.subscribe('foo/counter')
              .on('update', function(data) {
                  document.getElementById('update').innerHTML = data;
              }
          );
      }
   ```
   {: codeblock}

7. Change the function that is called on connection to the `subscribeToTopic` function you just created.
   ```
   .then(subscribeToTopic);

   ```
   {: codeblock}

8. Open the HTML file in a browser.



# Full example 
```
<html>
  <head>
   <title>JavaScript example</title>
    <script type="text/javascript" src="http://developer.reappt.io/clients/js/diffusion.js"></script>
    
  </head>
  <body>
    <div>
      <span>The value of foo/counter is: </span>
      <span id="update">Unknown</span>
    </div>

    <script type="text/javascript">
      function subscribeToTopic(session) {
          session.subscribe('foo/counter')
              .on('update', function(data) {
                  document.getElementById('update').innerHTML = data;
              }
          );
      }
      diffusion.connect({
          // Edit this line to include the URL of your Reappt service
          host : 'service-name.reappt.io',
          
          // To connect anonymously you can leave out the following parameters
          principal : 'user',
          credentials : 'password'
      }).then(subscribeToTopic);
    </script>
  </body>
</html>
```
{: codeblock}




## Get started
{: #get_started}

* [Getting started in JavaScript](http://developer.reappt.io/docs/manual/html/developerguide/apis/javascript/getting_started.html){:new_window}
* [Getting started in Android](http://developer.reappt.io/docs/manual/html/developerguide/apis/android/getting_started.html){:new_window}
* [Getting started in Apple](http://developer.reappt.io/docs/manual/html/developerguide/apis/apple/getting_started.html){:new_window}
* [Getting started in Java](http://developer.reappt.io/docs/manual/html/developerguide/apis/java/getting_started.html){:new_window}
* [Getting started in .NET](http://developer.reappt.io/docs/manual/html/developerguide/apis/dotnet/getting_started.html){:new_window}
* [Getting started in C](http://developer.reappt.io/docs/manual/html/developerguide/apis/c/getting_started_c.html){:new_window}

 
