---

copyright:

  years:  2017

lastupdated: "2017-03-15"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting Started with Xignite Market Data APIs
{: #gettingstarted_Xignite}

Xignite APIs provide access to real-time and reference market data making it easy for fintech developers to integrate stock quotes or other finacnial information with Internet of Things devices. 

To get up and running quickly with calling an Xignite API, follow these steps:
Register for free trial
https://market-data.xignite.com/IBM_Marketplace.html
You can choose one API for the trial. Your trial is for a maximum of 250 hits

A Word About Hits
• Most calls you make consume hits (some are free).
• The number of hits a call consumes depends on the API and your INPUT parameters (e.g. number of symbols).
• If you exceed your 250 trial hits, you will see an error message and will not be able to use the service for additional calls.

Our API Catalog
https://www.xignite.com/ProductS/
You can view the web services that Xignite offers here.
On our API catalog page you can filter APIs by asset class, frequency, data types and region.
Click on API List to go to the APIs and test form.

Web Service Page
On the first page of each of Xignite's 45 web services the data coverage and key data points are provided, as well as related services and where Xignite has sourced this data.

API List Page
The APIs are organized by group of related APIs. For instance APIs that list items will be grouped together, or chart APIs will be grouped as well.

Test Form
Choose the API you are interested in and navigate to the test form. The test form is designed to help you play with the API as you implement it. Drop downs and Type Ahead functionality are available for certain input parameters. Enter your parameters and click View Results. Then click the color coded URL for your parameters. Click on it to open a new tab and pull up the results. Full Output Documentation is available is you scroll to the bottom of the page.

Customizing Your API Calls
You can customize the output of each API by picking the fields you want to retrieve. This simplifies coding and speeds your calls by limiting network traffic.

Output
All our APIs support XML, JSON or CSV formats. You can choose to view the output in a Grid format, in XML, JSON or CSV. Just pick the tab you want and click “View Results” The output of the call is displayed in the format you choose.

Accessing Documentation
http://www.xignite.com/product/gold-metal/api/GetLastRealTimeMetalQuote
All our documentation is online or available for download on the web site. If you don’t see it, most likely we do not have it! There are four standard output values: Outcome, Message, Identiy and Delay. The Code Tab provides you with many useful technical resources!

Authenticating Your API Calls
We authenticate your calls using a token. You maintain your tokens using My Account. Tokens can be: 
- A random value we generate
- A mnemonic value you provide
- An IP address

#KnowledgeBase
http://www.xignite.com/Support/

#SDeveloper Documentation
http://www.xignite.com/developers

#SDKs
http://xignite.github.io/JavaSDK/
http://xignite.github.io/DotNetSDK/

#Pricing
http://www.xignite.com/pricing
