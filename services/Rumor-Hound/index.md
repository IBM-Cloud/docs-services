---

copyright: Accrete LLC

  years:  2018

lastupdated: "2017-2-25"

---

Function Name : getList
Description : This function gives you latest rumours requested

Input Parameters :
url = (optional) rumor link to search in db. If you are looking for specific rumour
text = (optional) source to search in db. To look for rumours from specific source
max_row_count = (default 50) Number of rows you can want to fetch. Maximum number of rows
that we can fetch is 100.
e.g. {"max_row_count": 4}

Output Format :
[{

               "acquirersymbol": "GD",
               "acquirercompany": "General Dynamics Corporation",
               "targetcompany": "Oshkosh Corporation",
               "targetsymbol": "OSK"
     },
     {
               "acquirersymbol": "LMT",
               "acquirercompany": "Lockheed Martin Corporation",
               "targetcompany": "Oshkosh Corporation",
               "targetsymbol": "OSK"
     },
     {
               "acquirersymbol": "RTN",
               "acquirercompany": "Raytheon Company",
               "targetcompany": "Oshkosh Corporation",
               "targetsymbol": "OSK"
     },
     {
               "acquirersymbol": "AAPL",
               "acquirercompany": "Apple Inc.",
               "targetcompany": "GoPro, Inc.",
               "targetsymbol": "GPRO"
     }
]

Function Name : getDetails

Description : This function provides the details of the rumours such as source, url, credibility,
recency, fundamental data, etc

InputParam :
target = acquiree symbol (targetsymbol)
acquirer = acquirer symbol

e.g. {"target":"NFLX","acquirer":"AAPL"}

Sample Output :
{
          "summary": {
                  "actionability": 8.889963586709149,
                  "credibility": 12.73
     },
     "fundamentals": {
                "targetdet": {
                       "grossmargins": 0,
                       "pe": 207.54,
                       "eps": 0.99,
                       "cash": 51,
                       "toplinesales": 0
               },
              "acquirerdet": {
                      "grossmargins": 0,
                      "pe": 18.75,
                      "eps": 9.19,
                      "cash": 12,
                      "toplinesales": 0
                }
        },
       "overview": {
               "targetdet": {
                      "symbol": "NFLX",
                      "marketcap": 89077.82,
                      "netmargins": 0,
                      "company": "Netflix, Inc.",
                      "industry": "CATV Systems",
                      "sector": "Services"
               },
              "acquirerdet": {
                     "symbol": "AAPL",
                     "marketcap": 893949.46,
                     "netmargins": 0,
                     "company": "Apple Inc.",
                     "industry": "Electronic Equipment",
                     "sector": "Consumer Goods"
              }
      },
     "priceinfo": {
           "targetdet": {
                 "weeklow52": 126.55,
                 "weekhigh52": 206.21,
                 "lasttrade": 206.85,
                 "yearprice": "#N/A"
           },
           "acquirerdet": {
                  "weeklow52": 115.75,
                  "weekhigh52": 177.2,
                  "lasttrade": 172.82,
                  "yearprice": "#N/A"
            }
       },
      "rumors": {
              "details": [{

                                     "SOURCE": "https://twitter.com/chheplo",
                                     "CREDIBILITY": 3.2,
                                     "URL": "https://twitter.com/chheplo/status/948255738173972480"
                               },
                               {
                                   "SOURCE": "https://twitter.com/sandroalberti",
                                   "CREDIBILITY": 3.2,
                                   "URL": "https://twitter.com/sandroalberti/status/948955615082287104"

                               },
                               {
                                   "SOURCE": "www.streetinsider.com",
                                   "CREDIBILITY": 6.33,
                                   "URL": "https://www.streetinsider.com/Analyst+Comments/Netflix+%28NFLX%29+Ramps+Higher+as+Analy
st+Assigns+40%25+Chance+of+an+Apple+%28AAPL%29+Takeover/13642814.html"

                               }
                      ]
           }
}