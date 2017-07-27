---

copyright:

  years:  2017

lastupdated: "2017-07-27"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Twilio Programmable Video
{: #gettingstarted_TwilioProgrammableVideo}

Twilio’s [Programmable Video](https://www.twilio.com/video){: new_window} makes
it easy to add real-time Video, Voice, and Screen-Sharing to your web
application. Build a rich, interactive web experience and keep your customers
entertained and supported while constantly coming back.
{: shortdesc}

## About

Today we’re going to go sans-servers and build out a sample Video application
on top of IBM’s awesome Bluemix. We’ll use an adaptation of our
[Node.js Quickstart Video Application](https://www.twilio.com/docs/api/video/quickstart-sample-apps){: new_window},
with our JavaScript Client library for the browser.  You’ll also need to verify
your browser has WebRTC support before continuing, and allow access to your
camera and microphone.

## Let's get started!

1. Sign into the [Twilio Console](https://www.twilio.com/console){: new_window}
   or [Register](https://www.twilio.com/try-twilio){: new_window} for a Free
   Account

1. If necessary, download and install the [Bluemix Command Line Interface](https://console.bluemix.net/docs/starters/install_cli.html){: new_window}
   - Change the API Endpoint and Login:

     ```
     bluemix api https://api.ng.bluemix.net
     bluemix login
     ```
     {: codeblock}

1. Log into Bluemix Console and create a Twilio App

   - Click 'Catalog' at the top of the screen
   - Enter 'twilio'

   ![Twilio app from Bluemix catalog](images/03-create-twilio-app.png)

1. In the following screen, enter your `Account SID` and `Auth Token` from the
   Twilio Console. In the Twilio Console, your credentials can be found here:

   ![Configure your Twilio Credentials](images/02-twilio-credentials.png)

1. Navigate to the API Key Creation Screen in the Twilio Console. Create a new
   API Key, saving both the `key` and the `secret` - you won’t be able to get it back again!

1. In the Bluemix Console, select 'Catalog' -> 'Apps' -> 'Cloud Foundry Apps'
   then select the `SDK for Node.js`. Name it something memorable.

1. In the Bluemix Dashboard, click on your Twilio Service under 'Services',
   then click the 'Create connection +' button. Connect it to your new Node.js
   App.

1. Navigate back to your Bluemix app and click ‘Runtime’ on the left sidebar.
   In environment variables, set two environment variables. Copy and paste the
   APP Sid and a Voice-capable phone number:

    ```bash
    TWILIO_TWIML_APP_SID
    TWILIO_NUMBER
    ```
    {: screen}

    ![Set Environment Variables](images/09-env-variables.png)

1. Locally, clone our sample application:

    ```bash
    git clone -b bluemix-quickstart https://github.com/TwilioDevEd/video-quickstart-js
    ```
    {: pre}

1. Deploy the application using the command line tools:

   ```bash
   bluemix app push <Your App Name>
   ```

1. In a browser which supports WebRTC, visit `<your Bluemix URL>`.  Preview
   your camera and join a room (may we suggest ‘twilio-bluemix’ ?)

1. Open a second browser with WebRTC support on a different machine*. Join the
   same room and verify the app works! Or use a second tab in the same browser
   - but this is more fun.

And with that you’ve built a serverless video chat room!  Feel free to share
that link around to show off the video room you built in under ten minutes(!).

Want to go even further with Twilio? You can find all of our [Node.js
communications application tutorials](https://www.twilio.com/docs/tutorials?filter-language=node&order_by=-popularity_rank){: new_window} on our [Documentation site](https://www.twilio.com/docs/){: new_window}.


We can’t wait to see what you build!
