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

If you are new to RabbitMQ, we recommend you read the guide [RabbitMQ for beginners before continuing](https://www.cloudamqp.com/blog/2015-05-18-part1-rabbitmq-for-beginners-what-is-rabbitmq.html?cm_mc_uid=22273308531414543392018&cm_mc_sid_50200000=1458671296).

<!-- Include a sentence to briefly introduce the steps. Examples: -->

###Steps to integrate app with the service.

Complete these steps to get started with the CloudAMQP service:

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

All AMQP client libraries work with CloudAMQP and there are AMQP client libraries for almost every platform. Sample code, links to recommended libraries and further information about the client libraries can be found in [the CloudAMQP documentation](https://www.cloudamqp.com/docs/index.html). 

1.  Add the client library to your dependencies file. The library will be downloaded automatically when you deploy your app. CloudAMQP recommended client libraries for different languages can be found here:      [Ruby](https://www.cloudamqp.com/docs/ruby.html){:new_window}, [Python](https://www.cloudamqp.com/docs/python.html){:new_window}, [Celery](https://www.cloudamqp.com/docs/celery.html){:new_window}, [node.js](https://www.cloudamqp.com/docs/nodejs.html){:new_window}, [PHP](https://www.cloudamqp.com/docs/php.html){:new_window}, [Java](https://www.cloudamqp.com/docs/java.html){:new_window}, [Clojure](https://www.cloudamqp.com/docs/clojure.html){:new_window}, [Go](https://www.cloudamqp.com/docs/go.html){:new_window}, [Android](https://www.cloudamqp.com/docs/android.html){:new_window}, [.NET](https://www.cloudamqp.com/docs/dotnet.html){:new_window}, [Perl](https://www.cloudamqp.com/docs/perl.html){:new_window} and [C](https://www.cloudamqp.com/docs/c.html){:new_window}. For example, in Ruby, open the Gemfile and add gem ‘bunny’. 
    
    ```
    gem 'bunny'
    ```
    {: pre}
2.  Copy code from the the same language-specific link as above. For example, in Ruby: 
    ```
    require "bunny" # don't forget to put gem "bunny" in your Gemfile 

    services = JSON.parse(ENV['VCAP_SERVICES'])
    cloudamqp_conf = services["cloudamqp"].first
    uri = cloudamqp_conf["credentials"]["uri"]

    b = Bunny.new uri
      
    b.start # start a communication session with the amqp server
      
    ch = b.create_channel # create a channel

    q = ch.queue("test") # declare a queue
      
    # declare a default direct exchange, which is bound to all queues
    e = ch.exchange("")

    # publish a message to the exchange, the message will be routed to the queue "test"
    e.publish("Hello, everybody!", key: value)
      
    # subscribe from the queue
    q.subscribe(block: true) do |delivery_info, properties, payload|
       puts "This is your message: " + payload + "\n\n"
       b.stop # close the connection
    end
    ```
    {: codeblock}

3. Set up connection Environment Variable: The connection and credential information for CloudAMQP is available in the Bluemix VCAP_SERVICES environment variable. It’s a nested JSON objected with all service credentials. 

<!-- Related links section: REQUIRED.
Related links display in the upper right of the getting started page. 
Ensure that you retain the lowercase anchor IDs (eg. {: #rellinks}) as shown in this template. These are used as IDs during transform and the doc framework keys off the IDs for display. 
The headings coded here are not actually used. The doc framework provides the correct headings. 
Also ensure that the related links stay in position at the end of this file or the doc framework will not display them properly.
Use {:new_window} for external links to open a new window.-->
<!-- Please delete all comments within the related links section to avoid breaking the build. Thanks. -->
# Related Links
[Plans and pricing](https://www.cloudamqp.com/plans.html){:new_window}
[FAQ](https://www.cloudamqp.com/docs/faq.html)
[Blog and news](https://www.cloudamqp.com/blog/index.html) 

{: #rellinks}
## Tutorials and Samples
[Ruby](https://www.cloudamqp.com/docs/ruby.html){:new_window} [Python](https://www.cloudamqp.com/docs/python.html){:new_window} [Celery](https://www.cloudamqp.com/docs/celery.html){:new_window} [node.js](https://www.cloudamqp.com/docs/nodejs.html){:new_window} [PHP](https://www.cloudamqp.com/docs/php.html){:new_window} 
[Java](https://www.cloudamqp.com/docs/java.html){:new_window}, [Clojure](https://www.cloudamqp.com/docs/clojure.html){:new_window}
[Go](https://www.cloudamqp.com/docs/go.html){:new_window} 
[Android](https://www.cloudamqp.com/docs/android.html){:new_window}
[.NET](https://www.cloudamqp.com/docs/dotnet.html){:new_window} 
[Perl](https://www.cloudamqp.com/docs/perl.html){:new_window} 
[C](https://www.cloudamqp.com/docs/c.html){:new_window}
{: #samples}


