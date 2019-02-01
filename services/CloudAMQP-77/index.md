---

copyright:

  years:  2018

lastupdated: "2018-08-15"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About CloudAMQP
{: #gettingstarted}

CloudAMQP automates every part of set up, running and scaling of RabbitMQ clusters. Let your team focus on what they do best - building your product. Leave server management and monitoring to the experts.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/camqp_3fd350bd-8e7d-4181-87c6-c4adb23bea0a.png)



{:shortdesc}

## Getting started

CloudAMQP is hosting managed RabbitMQ servers in the cloud. Message queues that let you pass messages between processes and other systems. 

Messages are published to a queue by a producer, the consumers can then get the messages from the queue when the consumer wants to handle the messages. In-between, it can route, buffer, and persist the messages according to rules you give it. 

Messages can be sent cross languages, platforms and OS, this way of handling messages decouple your processes and creates a highly scalable system. 

A complete beginner guide can be found [here](https://www.cloudamqp.com/blog/2015-05-18-part1-rabbitmq-for-beginners-what-is-rabbitmq.html){:new_window}.

To get started you need to sign up for a custom plan. What plan you want to use depends on your needs. We offer seven different plans, both dedicated clusters, individual servers and vhosts on shared clusters. Plan information can be found [here](https://www.cloudamqp.com/plans.html){:new_window}.

You can try CloudAMQP for free with the plan Little Lemur.

Fill information about your cluster and press "create". 2 minutes later you will have a perfectly configured and optimized RabbitMQ server up and running.

When your instance is created, press on details for your instance to find your username, password and connection URL for your hosted RabbitMQ instance.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/new-instance-details-mini_5467dd57-0a48-4138-9c89-431736f42a1a.jpg)

Start by downloading the client-library for your selected programming language. Developers usually have a number of options for AMQP client libraries, ask us if you need help or look into our documentation [here](https://www.cloudamqp.com/docs/index.html){:new_window}. 

The following example will use the synchronous client Bunny and publish a message and then consume it.
~~~~
require "bunny" # don't forget to put gem "bunny" in your Gemfile

b = Bunny.new ENV['CLOUDAMQP_URL']
b.start # start a communication session with the amqp server

q = b.queue("test1") # declare a queue

# declare default direct exchange which is bound to all queues
e = b.exchange("")

# publish a message to the exchange which then gets routed to the queue
e.publish("Hello, everybody!", :key => 'test1')

msg = q.pop[:payload] # get message from the queue

puts "This is the message: " + msg + "\n\n"

b.stop # close the connection
~~~~

RabbitMQ provides a web UI for management and monitoring of your RabbitMQ server. The RabbitMQ management interface is enabled by default in CloudAMQP and a link can be found on the details page for your CloudAMQP instance. 

From the management interface, it is possible to handle, create, delete and list queues. It is possible to monitor queue length, check message rate, change and add users permissions much more.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/new-rabbitmq-manager-mini_17c9ba7f-a4f1-4687-bb81-a6a68e3fba2f.jpg)

