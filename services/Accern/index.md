---
copyright:
  years:  2017
lastupdated: "2017-03-10"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Accern API
{: #gettingstarted}

Accern alerts you on actionable stories about U.S. public companies. By monitoring over 300 million public news, blog, social media websites, and financial documents, it identifies low-exposed stories and uses advanced data science to determine whether the stories are reliable and impactful.

By using this systematic approach, Accern is able to provide users with quick delivery of actionable stories before they are exposed to the mass media. This helps our users make quicker and more informed decisions in their investment strategies.

Existing users include, but are not limited to hedge funds, asset managers, equity researchers, news media, and Fortune 500 companies.
{:shortdesc}

## API access token

You need an API access token to receive data from Accern APIs. To request an API access token, please follow the steps below:

- Create an account on [Accern](https://app.accern.com/login){:new_window}
- Login to your Accern account.
- From the dropdown menu in the top-right corner of the app, click on the `API Tokens` option.
- Choose the number of API tokens and submit your request.

Once you have submitted the API token request, our team will follow-up and send you the authentication tokens via email.

## Authentication

To authenticate, provide your authentication token in the url by inserting it in the `TOKEN` part.

Shell
```shell
curl "http://feed.accern.com/v3/alphas?token=TOKEN"
```
{: codeblock}

Ruby
```ruby
require 'uri'
require 'net/http'

url = URI("http://feed.accern.com/v3/alphas?token=TOKEN")
http = Net::HTTP.new(url.host, url.port)
request = Net::HTTP::Get.new(url)
response = http.request(request)
puts response.read_body
```
{: codeblock}

Python
```python
import requests

url = "http://feed.accern.com/v3/alphas?token=TOKEN"
req = requests.get(url)
text_response = req.text # read response as Text
print(text_response)

json_response = req.json() # read response as JSON
print(json_response)
```
{: codeblock}

R
```r
if (!require("jsonlite")) install.packages("jsonlite")

url <- "http://feed.accern.com/v3/alphas?token=TOKEN"
response <- fromJSON(url)
print(response)
```
{: codeblock}

## Feed

`GET http://feed.accern.com/v3/alphas?token=TOKEN`

By default this request will return the most recent 100 documents.

Shell
```shell
curl "http://feed.accern.com/v3/alphas?token=TOKEN"
```
{: codeblock}

Ruby
```ruby
url = URI("http://feed.accern.com/v3/alphas?token=TOKEN")
```
{: codeblock}

Python
```python
url = "http://feed.accern.com/v3/alphas?token=TOKEN"
```
{: codeblock}

R
```R
url <- "http://feed.accern.com/v3/alphas?token=TOKEN"
```
{: codeblock}

> The above url returns the most recent 100 documents.

JSON Format
```json
[
  {
    "id": 1774184,
    "article_id": {
      "$oid": "589b44a569fe9f7f77024f4a"
    },
    "article_sentiment": 0.098,
    "article_traffic": null,
    "article_type": "blog",
    "article_url": "http://feedproxy.google.com/~r/RedmondPie/~3/mF7K04DF1y4/",
    "author_id": null,
    "correlations": null,
    "entities": [
      {
        "name": "Apple Inc.",
        "type": "Public",
        "index": "S&P 500, Russell 1000, Russell 3000, Wilshire 5000, BARRON'S 400, NASDAQ 100",
        "region": "North America",
        "sector": "Technology",
        "ticker": "AAPL",
        "country": "United States",
        "exchange": "NASDAQ",
        "industry": "Computer Manufacturing",
        "entity_id": "EQ0010169500001000",
        "global_id": "BBG000B9XRY4",
        "competitors": [
          "GOOG",
          "HPQ"
        ]
      },
      {
        "name": "Amazon.com, Inc.",
        "type": "Public",
        "index": "S&P 500, Russell 1000, Russell 3000, Wilshire 5000, NASDAQ 100",
        "region": "North America",
        "sector": "Consumer Services",
        "ticker": "AMZN",
        "country": "United States",
        "exchange": "NASDAQ",
        "industry": "Catalog/Specialty Distribution",
        "entity_id": "EQ0021695200001000",
        "global_id": "BBG000BVPV84",
        "competitors": [
          "AAPL",
          "BKS"
        ]
      }
    ],
    "event_author_rank": [
      {
        "author_rank": 4,
        "event_group": "Employment Actions"
      },
      {
        "author_rank": 4,
        "event_group": "Employment Actions"
      }
    ],
    "event_groups": [
      {
        "type": "Recruitment",
        "group": "Employment Actions"
      },
      {
        "type": "Layoff",
        "group": "Employment Actions"
      }
    ],
    "event_impact_score": {
      "overall": 40.88471673254282,
      "on_entities": [
        {
          "entity": "AAPL",
          "on_entity": 31
        },
        {
          "entity": "AMZN",
          "on_entity": 32
        }
      ]
    },
    "event_source_rank": [
      {
        "event_group": "Employment Actions",
        "source_rank": 6
      },
      {
        "event_group": "Employment Actions",
        "source_rank": 6
      }
    ],
    "event_summary": {
      "group": "",
      "theme": "",
      "topic": "",
      "action": "",
      "sub-theme": "",
      "acting_party": ""
    },
    "first_mention": false,
    "harvested_at": "2017-02-08 16:17:39 UTC",
    "overall_author_rank": 5,
    "overall_source_rank": 6,
    "source_id": null,
    "story_id": {
      "$oid": "589a6b6469fe9f7f70ac1df6"
    },
    "story_saturation": "high",
    "story_sentiment": 0.072,
    "story_shares": null,
    "story_volume": 58
  }
]
```
{: codeblock}

## Filtering

Parameter | Description
-----------| ------------
last_id	      | Returns the latest 100 documents that came after the provided id.  Used to prevent duplicates while keeping in sync (see [streaming](#streaming) section).
index         | Filters documents by the index, see below table for supported indexes. To filter by multiple indexes pass a comma separated list of indexes.
ticker         | Filters documents by ticker. To filter by multiple tickers pass a comma separated list of tickers.

### Allowed index values

index					 | expected query string value
-----------------|----------------------
S&P 500				| sp500
Russell 1000		| russell1000
Russell 3000		| russell3000
Wilshire 5000		| wilshire5000
Barron's 400		| barrons400
DOW 30				| dow30

### Filter by last_id

Shell
```shell
curl "http://feed.accern.com/v3/alphas?last_id=1774184&token=TOKEN"
```
{: codeblock}

Ruby
```ruby
url = URI("http://feed.accern.com/v3/alphas?last_id=1774184&token=TOKEN")
```
{: codeblock}

Python
```python
url = "http://feed.accern.com/v3/alphas?last_id=1774184&token=TOKEN"
```
{: codeblock}

R
```R
url <- "http://feed.accern.com/v3/alphas?last_id=1774184&token=TOKEN"
```
{: codeblock}

### Filter by index

Shell
```shell
curl "http://feed.accern.com/v3/alphas?index=sp500&token=TOKEN"
```
{: codeblock}

Ruby
```ruby
url = URI("http://feed.accern.com/v3/alphas?index=sp500&token=TOKEN")
```
{: codeblock}

Python
```python
url = "http://feed.accern.com/v3/alphas?index=sp500&token=TOKEN"
```
{: codeblock}

R
```R
url <- "http://feed.accern.com/v3/alphas?index=sp500&token=TOKEN"
```
{: codeblock}

### Filter by multiple indexes

Shell
```shell
curl "http://feed.accern.com/v3/alphas?index=sp500,dow30&token=TOKEN"
```
{: codeblock}

Ruby
```ruby
url = URI("http://feed.accern.com/v3/alphas?index=sp500,dow30&token=TOKEN")
```
{: codeblock}

Python
```python
url = "http://feed.accern.com/v3/alphas?index=sp500,dow30&token=TOKEN"
```
{: codeblock}

R
```R
url <- "http://feed.accern.com/v3/alphas?index=sp500,dow30&token=TOKEN"
```
{: codeblock}

### Filter by ticker

Shell
```shell
curl "http://feed.accern.com/v3/alphas?ticker=amzn&token=TOKEN"
```
{: codeblock}

Ruby
```ruby
url = URI("http://feed.accern.com/v3/alphas?ticker=amzn&token=TOKEN")
```
{: codeblock}

Python
```python
url = "http://feed.accern.com/v3/alphas?ticker=amzn&token=TOKEN"
```
{: codeblock}

R
```R
url <- "http://feed.accern.com/v3/alphas?ticker=amzn&token=TOKEN"
```
{: codeblock}

### Filter by multiple tickers

Shell
```shell
curl "http://feed.accern.com/v3/alphas?ticker=aapl,amzn&token=TOKEN"
```
{: codeblock}

Ruby
```ruby
url = URI("http://feed.accern.com/v3/alphas?ticker=aapl,amzn&token=TOKEN")
```
{: codeblock}

Python
```python
url = "http://feed.accern.com/v3/alphas?ticker=aapl,amzn&token=TOKEN"
```
{: codeblock}

R
```R
url <- "http://feed.accern.com/v3/alphas?ticker=aapl,amzn&token=TOKEN"
```
{: codeblock}

## File Format

Shell
```shell
curl "http://feed.accern.com/v3/alphas.csv?token=TOKEN"
```
{: codeblock}

Ruby
```ruby
url = URI("http://feed.accern.com/v3/alphas.csv?token=TOKEN")
```
{: codeblock}

Python
```python
url = "http://feed.accern.com/v3/alphas.csv?token=TOKEN"
```
{: codeblock}

R
```R
url <- "http://feed.accern.com/v3/alphas.csv?token=TOKEN"
```
{: codeblock}


By default the response from the API feed is in JSON format. But if you append .csv you will get the data in CSV format.

CSV Columns                |
---------------------------|
id                         |
article_id                 |
story_id                   |
harvested_at               |
entities_name_1            |
entities_ticker_1          |
entities_global_id_1       |
entities_entity_id_1       |
entities_type_1            |
entities_exchange_1        |
entities_sector_1          |
entities_industry_1        |
entities_country_1         |
entities_region_1          |
entities_index_1           |
entities_competitors_1     |
entities_name_2            |
entities_ticker_2          |
entities_global_id_2       |
entities_entity_id_2       |
entities_type_2            |
entities_exchange_2        |
entities_sector_2          |
entities_industry_2        |
entities_country_2         |
entities_region_2          |
entities_index_2           |
entities_competitors_2     |
event_groups_group_1       |
event_groups_type_1        |
event_groups_group_2       |
event_groups_type_2        |
story_sentiment            |
story_saturation           |
story_volume               |
first_mention              |
article_type               |
article_sentiment          |
overall_source_rank        |
event_source_rank_1        |
event_source_rank_2        |
overall_author_rank        |
event_author_rank_1        |
event_author_rank_2        |
event_impact_score_overall |
event_impact_score_entity_1|
event_impact_score_entity_2|
event_summary_group        |
event_summary_theme        |
event_summary_topic        |
event_summary_action       |
event_summary_sub-theme    |
event_summary_acting_party |
article_url                |

## Streaming

To stay in sync with the API you make a request with `last_id=[lastest document id]` then grab the id of the latest document that comes back and repeat. We packaged this logic up in our Accern gem, to install follow the instructions on the [repo](https://github.com/accern/accern).

## Backfill

The API allows you to access data going back 30 days, anything older we provide via other means. To start from 30 days ago and move forward you have to provide `last_id=0`. Then continue to hit the API while setting the `last_id` query string parameter.

## Related Links
{: #rellinks notoc}

### Api Reference
{: #api} [Overview of the Accern API](http://docs.accern.com/#accern-overview) {:new_window}

{: #api} [Detailed description of Accern analytics](http://docs.accern.com/#accern-analytics) {:new_window}

### Resources
{: #general} [Accern resources](https://www.accern.com/resources/) {:new_window}
