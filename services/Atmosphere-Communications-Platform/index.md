---

copyright:

  years:  2019

lastupdated: "2019-04-01"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About Atmosphere® Communications Platform
{: #gettingstarted}

Integrated with IBM Watson applications and capabilities, IntelePeer’s Atmosphere® Communications Platform lets you seamlessly integrate omni-channel communications into your customer experience and business workflows for a complete communications experience. Designed to solve the challenges and complex needs of mid-size to large enterprises, Atmosphere® Communications Platform can be used to deliver world-class communications.

{:shortdesc}

## Getting started

In order to use Watson Assistant through SmartFlows, you must already have an IBM Cloud account with Assistant enabled.

![Documentation image](https://mp.s81c.com/pwb-production/markdownBuilder_image_/SmartflowsIBM_8e3504af-7ba4-4ed0-a47a-fc517e34ac17_91e1f107-9272-4ae6-9659-150bff1d7e35.PNG)



Login to your IntelePeer Customer Portal at customer.intelepeer.com. 

Click on the Atmosphere® SmartFlows icon on the Home screen.

Start building your customized workflow. 

Add in IBM Watson technology by dragging and dropping the Watson Assistant action into your flow wherever it's needed. 

Click on the Watson Assistant action to get the inputs panel on the right of the screen. 

Enter the following for the input fields:

Assistant Credentials
Sign in to Assistant using your IBM credentials. These can be found in the API details of the configured Watson Assistant.

Assistant URL
Enter the Assistant URL found in the API details of the configured Watson Assistant. 

WorkSpace ID
Supply your ID which can be found within the API details of the Assistant Skill associated with the configured Watson Assistant. 

Text/Message
Here you will enter the content of the message or the phone call.  To use Assistant for an incoming SMS, for example, select the variable assigned to the pre-built Incoming SMS block and drag it down to the Text/Message field. 


![Documentation image](https://mp.s81c.com/pwb-production/markdownBuilder_image_/Smartflows-IBM-2_3e19fe40-26ed-43b8-9472-1683e9b048bc_fc54963a-38f8-48c5-bb38-5d3c47404cf3.PNG)



Variables

The Watson Assistant action creates several variables. These variables can be used later on in a flow through the SMS, External Web Call, Dial action, or more.

$WATSONASSIST_#.responsebody
The entire response from the Watson Assistant.

$WATSONASSIST _#.statuscode
The code that indicates the status of the API response (i.e. 200 = success, 404 = not found, 403 = forbidden).

$WATSONASSIST _#.response.output.text[0]
The response that was returned by Watson Assistant.

Further enhance your communications with our other Watson Assistant actions - Sentiment, Tonality, Detect Language, and Translate.

Learn how:

[Sentiment](https://www.intelepeer.com/products/documentation/smartflows-glossary/sentiment/){:new_window}

[Tonality](https://www.intelepeer.com/products/documentation/smartflows-glossary/tonality/){:new_window}

[Detect language](https://www.intelepeer.com/products/documentation/smartflows-glossary/detect-language/){:new_window}

[Translate](https://www.intelepeer.com/products/documentation/smartflows-glossary/translate/){:new_window}

