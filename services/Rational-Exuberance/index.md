# Rational Exuberance
---

copyright:
  years: 2018
lastupdated: "2018-03-27"

---


# Overview
{: #introduction}
<!--
<span style="color:gray">Overview</span> <a name = "introduction"></a> 
Last Updated: 2018-02-27 | [Edit in GitHub](http://github.com/accreteai)
-->

Rational Exuberance, our contextually adaptive and learning Fedspeak parser, is designed to help buy and sell side analysts refine forecasting assumptions based on hawkish/dovish sentiment divergences between the FOMC and general market chatter. Rational Exuberance can also help traders make tactical changes in position sizing and better hedge rate-sensitive positions.

## Getting Started
{: #getting_started}
<!--
<span style="color:gray">Getting Started</span><a name = "getting started"></a>
 -->

You need an API access token to receive data from Accrete's Rational Exuberance API. To request an API access token, please follow the steps below: 

  - Visit [accrete.ai](http://accrete.ai).
  - Click 'Sign Up/Login' on the top right corner of the page.
  - Select 'Sign Up'.
  - Complete the form. 
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
  __addAwareness__
  
  __Description__: 

    API call to train our awareness cloud to pay attention to ideas that you think are relevant to the FOMC. This microservice pushes filtered news taking into account user defined context.   

  __Input Data__: 

    URL or formatted text

  __Method: GET__

    eg:  :  http://169.60.176.152:8088/api/awareness/articles/add  

```javascript
__Output Data__: 

Article id of newly added article

```

__Function Name__: 
  __summarizeArticle__
  
  __Description__: 

    Reduce your research burden by calling this API to ingest and summarize articles that are relevant to employment and inflation. 

  __Input Data__: 

    Article id (mandatory)

  __Method: GET__ 

    eg:  http://169.60.176.152:8088/api/awareness/articles/summarize 

```javascript
__Output Data__: 

    Summary of given article

```

__Function Name__: 
  __awarenessSynthesis__
  
  __Description__:

  Pushes summarized versions of contextually relevant articles that pass through our awareness cloud along with sentiment measures of those articles. 

  __Input Data__: 

  URL:  article id (mandatory)  

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/awareness/articles/read
  
  
```javascript
__Output Data__:  
  
Summary and sentiment weighted keywords for given article

```
__Function Name__: 
  __contextuallyRelevantEmploymentArticles__
  
  __Description__:

  Awareness cloud continously reads and understands vast volumes of information in the context of the FOMC's employment mandate.

  __Input Data__: 

  (optional) date = value, default is today

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/knowledge/employment/articles/streaming
  
```javascript
__Output Data__:  
  
Summary and sentiment weighted keywords for given article

```
__Function Name__: 
  __contextuallyRelevantInflationArticles__
  
  __Description__:

  Awareness cloud continuously reads and understands huge volumes of information in the context of the FOMC's inflation mandate

  __Input Data__: 

  URL:  (optional) date = value, default is today  

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/knowledge/inflation/articles/streaming
  
  
```javascript
__Output Data__:  
  
All relevant inflation article ids from Awareness cloud for given time range

```

__Function Name__: 
  __fomcGovernorSentimentDrilldown__
  
  __Description__:

  Continuously reads and understands individual FOMC Governor communications, pushing key topics driving each Governor's hawkish or dovish sentiment 

  __Input Data__: 
  
  (mandatory) startdate = value, enddate = value, governor name

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/semantic/benchmark/governor/influence/getDetails
  
  
```javascript
__Output Data__:  
  
Date, time and collection of parameters with mentions for the specific governor

```

__Function Name__: 
  __fomcGovernorCrossoverLikelihoodDrilldown__
  
  __Description__:

 Continuously reads and understands individual FOMC Governor communications in the context of specific topics driving each Governor's crossover likelihood, a function of sentiment centricity and swing momentum.

  __Input Data__: 

  (mandatory) startdate = value, enddate = value, governor name  

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/semantic/benchmark/governor/crossover/getDetails
  
  
```javascript
__Output Data__:  
  
Date, time and collection of parameters with mentions for the specific governor

```

__Function Name__: 
  __fomcGovernorSentimentAndInfluence__
  
  __Description__:

  Continuously reads and understands individual FOMC Governor communications and attributes relative sentiment and influence weights in real time 

  __Input Data__: 

  (mandatory) startdate = value, enddate = value

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/semantic/benchmark/governor/influence
  
  
```javascript
__Output Data__:  
  
Relative influence by governor; current governor sentiment; aggregate FOMC sentiment; week-over-week sentiment delta; month-over-month sentiment delta; parameterize-able sentiment deltas
```

__Function Name__: 
  __fomcGovernorCrossoverLikelihood__
  
  __Description__:

  Continuously reads and understands individual FOMC Governor communications and attributes relative crossover likelihood based on sentiment centricity and crossover momentum in real-time

  __Input Data__: 

  (mandatory) startdate = value, enddate = value  

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/semantic/benchmark/governor/crossover/
  
  
```javascript
__Output Data__:  
  
Relative influence by governor; current governor crossover likelihood; current governor crossover momentum; aggregate FOMC crossover likelihood; week-over-week crossover likelihood delta; month-over-month crossover likelihood delta; parameterize-able crossover likelihood deltas

```

__Function Name__: 
  __divergentSentimentTracker__
  
  __Description__:

  Real-time processing and sentiment measurement of official FOMC communications, relevant market chatter and economic releases help users identify key divergences between the FOMC's interpretation of key economic numbers and the market's interpretation of key economic numbers.

  __Input Data__: 

  (mandatory) startdate = value, enddate = value, (optional) scorep = default is combined/inflation/employment; (mandatory) benchmark = default isyes/no; (optinal) marketchatter = default is no/yes; (optional) fomcsentiment = default is yes/no  

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/semantic/benchmark/sentiment
  
  
```javascript
__Output Data__:  
  
Temporal index scored between -10 (hawkish) and +10 (dovish) providing date, time, FOMC sentiment, Market Chatter sentiment and benchmark data

Benchmark components include PCE Core, PCE Headline, CPI Core; CPI Headlines; Average Hourly Earnings; Unit Labor Cost; Manufacturing ISM-Prices Pad; University of Michigan Inflation Expectations; 10 Yr. Breakeven Rates; 5yr/5yr Forward Breakeven Inflation Rates; Non-farm payrolls; U3 Unemployment Rate; U6 Unemployment Rate; Weekly Jobless Claims; Job Openings; NFIB Jobs Data.

```


__Function Name__: 
  __actionableInsights__
  
  __Description__:

  Provides users with an Accrete Synthetic Fed Futures yield that adjusts the front month 30 Day Fed Futures contract based on divergences between hawkish/dovish sentiment of the FOMC and market chatter in the context of inflation and employment. Continuously estimates a fair value for the 30 Day Fed Funds Futures by ingesting and contextualizing official Fed Communications, FOMC Governor Sentiment & Influence and FOMC Governor Crossover Likelihood. Forecasts FOMC rate decisions and attributes real time probability scores to forecasts. Pushes entry and exit signals in 91 Day U.S. T-bill yield, offering users and off the shelf alpha generating interest rate system. Users can incorporate our insights to build proprietary models, improve existing trading and risk systems or create custom dashboards.

  __Input Data__: 

  URL:  article id (mandatory)  

  __Method: GET__

  Eg. http://169.60.176.152:8088/api/awareness/articles/read
  
  
```javascript
__Output Data__:  
  
Summary and sentiment weighted keywords for given article

```