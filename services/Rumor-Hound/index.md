---
copyright:
  years:  2018
lastupdated: "2017-03-15"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Rumor Hound 
{: #gettingstarted}

Analysts, portfolio managers and traders struggle to keep ahead of market moving merger and acquisition rumors because actionable m&a rumors can emanate from any one of countless digital data sources. Rumor Hound solves this problem by continuously scouring tens of thousands of public, digital data sources in real time to find actionable m&a rumors that haven't yet been priced into the stock. Rumor Hound understands what an actionable m&a rumor looks like in all its linguistic nuance. When Rumor Hound finds a rumor, the rumor is pushed to users via API, dashboard, customizable filters and notifications along with a score that measures the credibility of the source based on site demographics, social media influence, Alexa rankings, etc. Transcending the black box, Rumor Hound provides users with not just the credibility score but also the source URL where the rumor was found as well as the rumor snippet itself so that users can validate for themselves the action-ability of the rumor. We are observing that m&a rumors that emanate from low credibility sources that gain momentum and are picked up by higher credibility sources tend to move prices. 

Through our Rumor Hound API, customers can access historical Rumor Hound data on hundreds of stocks. The Rumor Hound API covers m&a rumors for several thousand stocks. We continue to model Rumor Hound insights and as we identify predictive patterns, we will be happy to share reproducible research and data with API customers.

You need an API access token to receive data from Accrete's Rumor Hound API. To request an API access token, please follow the steps below: 

  - Visit [accrete.ai](http://accrete.ai).
  - Click 'Sign Up/Login' on the top right corner of the page.
  - Select 'Sign Up'.
  - Complete the form. 
  - Select Rumor Hound.
  - Select 'API' as delivery method. 
  - Select 'Submit'.
  
Once you've submitted your registration, an Accrete representative will reach out to you and provide the appropriate API credentials by email.

## Authentication
{: #authentication}
<!--
<span style="color:gray">Authentication</span><a name = "authentication"></a>
-->

To authenticate, please follow the instructions provided in the email containing your API credentials. 

## Methods
{: #method}
<!--
<span style="color:gray">Methods</span>  <a name = "method"></a>
-->

__Function Name__:
  __getList__
  
  __Description__: 

    This function gives you a list of the latest rumors.

  __Input Parameters__: 

    url = (optional) rumor link to search in db if you are looking for a specific rumor.
    text = (optional) source to search in db to look for rumors from a specific source. 
    Max_row_count = (default 50) Number of rows you want to fetch. Max is 100 rows. 
	
	e.g. {"max_row_count":4}

```javascript
__Output Format__: 
[{  
  "acquirersymbol":"GD",
  "acquirercompany":"General Dynamics Corporation",
  "targetcompany":"Oshkosh Corporation",    
  "targetsymol":"OSK"    
},
{
  "acquirersymbol":"LMT",
  "acquirercompany":"Lockheed Martin Corporation",
  "targetcompany":"Oshkosh Corporation",    
  "targetsymol":"OSK"  
},
{
  "acquirersymbol":"RTN",
  "acquirercompany":"Raytheon Company",
  "targetcompany":"Oshkosh Corporation",    
  "targetsymol":"OSK"    
},
{
  "acquirersymbol":"AAPL",
  "acquirercompany":"Apple Inc.",
  "targetcompany":"GoPro, Inc.",    
  "targetsymol":"GPRO"    
}]

```



__Function Name__: 
  __getDetails__
  
  __Description__: 

    This function provides the details of the rumors such as source, url, credibility, recency, fundamental data, etc.

  __Input Parameters__: 

    target = acquire symbol (targetsymbol)
    acquirer = acquirer symbol
  
    e.g. {"target":"NFLX","aquirer":"AAPL"}

```javascript
__Output Format__: 

[  
      "summary":{    
          "actionability": 8.889963586709149,      
          "credibility ": 12.73
      },   
      "fundamentals":{    
          "targetdet": {      
          	"grossmargins": 0,      
          	"pe": 207.54,      
          	"eps":0.99,      
          	"cash":51,
          	"toplinesales":0  
          },
          "acquirerdet": {      
          	"grossmargins": 0,      
          	"pe": 18.75,      
          	"eps":9.19,      
          	"cash":12,
          	"toplinesales":0 
          }
     },     
     "overview":{   
              "targetdet":{      
        	          "symbol": "NFLX",      
                         "marketcap": 89077.82,      
         	          "netmargins": 0,
	          "company": "Netflix, Inc.",
                        "industry": "CATV Systems",
                        "sector": "Services"                                       
    
      	},   
      	"aquirerdet":{      
        	          "symbol": "AAPL",      
                         "marketcap": 893949.46,      
         	          "netmargins": 0,
	          "company": "Apple, Inc.",
                        "industry": "Electronic Equipment",
                        "sector": "Consumer Goods"                                     
    
      	}
   }, 
   "rumors":{   
              "details":[{      
        	          "SOURCE": "https://twitter.com/chheplo",      
                         "CREDIBILITY": 3.2,      
         	          "URL": "https://twitter.com/chheplo/status/948255738173972480",
	          
    
      	}, 
              {
          "SOURCE": "https://twitter.com/sandroalberti",      
                         "CREDIBILITY": 3.2,      
         	          "URL": "https://twitter.com/sandroalberti/status/948955615082287104",
             },
             {
	           "SOURCE": "www.streetinsider.com",      
                         "CREDIBILITY": 6.33,      
         	          "URL": "https://www.streetinsider.com/Analyst/Takeover/13642814.html",
             }

          
      	
   }]

}]
     
```