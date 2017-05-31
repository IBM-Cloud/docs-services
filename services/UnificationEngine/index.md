---

copyright:

  years:  2017

lastupdated: "2017-05-30"

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


To integrate your app with the service, follow these steps:

1. Register as a developer in UnificationEngine developer portal at https://developer.unificationengine.com/.

![Register](register.png)
        
2. Create an app in UnificationEngine by providing app name at https://developer.unificationengine.com/apps. Once the app is created it will automatically generate an app key  [APP_KEY] and secret [APP_SECRET]. This key and secret is used to create a user for an app.

![Create App](createApp.png)

![App Details](appDetails.png)

3. Add a connector from the available list of connectors in UnificationEngine to the app you have created in developer portal using the 'Add Connector' button.

![Add Connector](addConnector.png)

4. Create a user for an app in UnificationEngine. On successful creation of a user, an access key [USER_ACCESS_KEY] and secret [USER_ACCESS_KEY]  for the user will be returned as response, which is required for all further api calls like add connection, sent message etc ( https://docs.unificationengine.com/#create-user ).

5. Add a connection to the user of the app ( https://docs.unificationengine.com/#add-connection ).

6. Send a message from your connector ( https://docs.unificationengine.com/#send-message ).

![Connector Details](connectorDetails.png)


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
