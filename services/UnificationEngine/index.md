---

copyright:

  years:  2017

lastupdated: "2017-06-13"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}



# Getting started with UnificationEngine
{: #gettingstarted_UnificationEngine}


UnificationEngine (UE) is an intelligent IoT messaging platform that solves IoT challanges for users, developers, and manufacturers by providing security, interoperability, and convenience. With a single, integrated API, UE simplifies both the user onboarding and device provisioning experiences.
{:shortdesc}


To integrate your app with UnificationEngine, follow these steps:

1. Register as a developer in UnificationEngine developer portal at https://developer.unificationengine.com/.
![Register](register.png) 
2. Create an app in UnificationEngine by providing app name at https://developer.unificationengine.com/apps. Once the app is created it will automatically generate an app key  [APP_KEY] and secret [APP_SECRET]. This key and secret is used to create a user for an app.
![Create App](createApp.png)
![App Details](appDetails.png)
3. Add a connector from the available list of connectors in UnificationEngine to the app you have created in developer portal using the 'Add Connector' button.
![Add Connector](addConnector.png)
4. Create a user for an app in UnificationEngine. On successful creation of a user, an access key [USER_ACCESS_KEY] and secret [USER_ACCESS_SECRET]  for the user will be returned as response, which is required for all further api calls like add connection, sent message etc ( https://docs.unificationengine.com/#create-user ).

  ```
  curl -XPOST https://apiv2.unificationengine.com/v2/user/create -u APP_KEY:APP_SECRET –data ’{}’ -k
  ```
  {: pre}

  The response for the create user will be something like:

  ```
 {
   "status": 200,
   "info": "OK", 
   "uri":"user://USER_ACCESS_KEY:USER_ACCESS_SECRET@"
  }
  ```
  {: pre}

5. Add a connection to the user of the app ( https://docs.unificationengine.com/#add-connection).

  ```
  curl -XPOST https://apiv2.unificationengine.com/v2/connection/add -u USER_ACCESS_KEY:USER_ACCESS_SECRET
  --data'{"uri":"CONNECTOR_SCHEME://CLIENT_ID:CLIENT_SECRET@CONNECTOR_SCHEME.com","name":"UNIQUE_CONNECTION_NAME"}'
  ```
  
  ![Connector Details](connectorDetails.png)
- **USER_ACCESS_KEY**  -  your access key
- **USER_ACCESS_SECRET**  -  your access secret
- **CONNECTOR_SCHEME**  -  the scheme of the connector
- **CLIENT_ID**  -  the client id of the respective service/channel
- **CLIENT_SECRET**  -   the client secret of the respective service/channel
- **UNIQUE_CONNECTION_NAME**  -   a unique name for the connection
  
  The success response for an add connection will be something like:

  ```
  {
   "status": 200,
   "info": "OK"
  } 
  ```
  {: pre}

6. Send a message from your connector ( https://docs.unificationengine.com/#send-message ).

  ```
  curl -XPOST https://apiv2.unificationengine.com/v2/message/send  -u USER_ACCESS_KEY: USER_ACCESS_SECRET
  --data "{ \"message\": { \"receivers\": [{\"name\": \"name\", \"address\": \"TO_ADDRESS\" ,
  \"Connector\": \" UNIQUE_CONNECTION_NAME \"}],\"sender\": {\"address\": \" FROM_ADDRESS \"  },
  \"parts\": [{\"id\": \"1\",\"contentType\": \" text/plain \", \"data\":\"test message body\" ,
  \"size\":MESSAGE_BODY_SIZE,\"type\": \"body\",\"sort\":0}]}}"
  ```
  {: pre}


<!-- Related links section: REQUIRED but moved to toc file (in your same folder).  Edit there by adding the following:

{: .navgroup id="learn"}
    index.md

    {: .topicgroup}
    Related links
        [UnificationEngine Developer Account](https://developer.unificationengine.com/)
    {: .navgroup-end}

To add related links, indent the 8 spaces, put the name of the link in [] and the URL in (), like so:
        [UnificationEngine Developer Account](https://developer.unificationengine.com/)
    
If you have API references to add, leave a blank line under the previous navgroup and then add:

    {: .navgroup id="reference"}
    Reference
        [API Documentation](https://docs.unificationengine.com)
    {: .navgroup-end}
-->
