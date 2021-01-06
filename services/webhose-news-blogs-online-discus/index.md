---

copyright:

  years:  2021

lastupdated: "2021-01-03"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About 
{: #gettingstarted}

Webhose is the leading web data provider transforming unstructured web content into machine-readable data feeds. Webhose’s data feeds and historical archives include multiple data sources such as news sites, online discussions, dark networks, and much more. Webhose delivers comprehensive, up-to-the-minute, relevant coverage of the open, deep, and dark web to enterprise-level customers in a wide range of verticals.
[block:html]
{
  "html": "<div class=\"mt-4\"></div>"
}
[/block]
In a world where online data growth is exponential, getting access to quality and structured web data is often a complex and expensive challenge. Organizations need access to structured web data for a wide range of applications, including marketing technology, financial analysis, cybersecurity, market research, machine learning applications, and more. With access to broad and diversified coverage of the open, deep, and dark networks, these organizations can focus on the data analysis while we focus on the data collection.
[block:html]
{
  "html": "<div class=\"mt-4\"></div>"
}
[/block]
Webhose’s machine-readable data feeds are simple, easy-to-integrate, and more cost-effective than any alternative on the market. Its granular filtering capabilities and scalable data plans are currently in use by hundreds of leading enterprise organizations all over the world. 
[block:html]
{
  "html": "<div class=\"mt-4\"></div>"
}
[/block]
Webhose is constantly engaged in developing cutting-edge technologies to maintain its role as a market leader in current and future data verticals while keeping its service cost-effective with superior enterprise-grade customer service.

[block:html]
{
  "html": "<div class=\"webhose-json-wrap\">\n\n  <p class=\"mb-0\">{</p>\n  <p class=\"mb-0 pw-1\">\"we\": <span class=\"value\">\"crawl\"</span>,</p>\n  <p class=\"mb-0 pw-1\">\"what\": <span class=\"value\">\"the web\"</span>,</p>\n    <p class=\"mb-0 pw-1\">\"why\": <span class=\"value\">\"so you don't have to\"</span></p>\n  <p class=\"mb-0\">}</p>\n\n</div>\n\n<style>\n.webhose-json-wrap {\n margin-top: -8px !important;\n}\n.webhose-json-wrap p {\n font-size: 14px !important;  \n  font-family: var(--md-code-font,SFMono-Regular,Consolas,Liberation Mono,Menlo,Courier,monospace) !important;\n  color: #F3F3F3 !important;\n  padding-left: 10px !important;\n }\n  \n.webhose-json-wrap .title {\n  \tbackground-color: #1e3a58 !important;  \n  padding: 10px 15px !important;\n}\n  \n .webhose-json-wrap span.value {\n   color: #01FF70 !important;\n  }\n  \n  .webhose-json-wrap .pw-1 {\n    padding-left: 20px !important; \n  }\n \n</style>",
  "sidebar": true
}
[/block]

[block:html]
{
  "html": "<div class=\"mb-5\"></div>"
}
[/block]

{:shortdesc}

## Getting started

In the following sections, we've gathered detailed information for you to learn about using Webhose.

  * Modify your billing or personal information in the *Account Settings* section.
  * Jump right in and take a peek into the repositories by building and running your test queries on the *API Playground*.
  * View usage stats and the latest queries in the *Dashboard*.

Webhose delivers broad and diversified coverage of the internet to enterprise-level customers in a wide range of web data verticals. Using our APIs you can filter the data to get relevant, comprehensive, up-to-date feeds that you can consume on-demand.

On the **Open Web**, Webhose supports multiple verticals which you can access via an API:

  * **News API** - Articles published in news outlets.
  * **Blogs API** - Self-published blogs by individual authors.
  * **Online Discussions API** - Discussions across message boards, Q&A pages and forums.
  * **Reviews API** - Posts and conversations on review sites.
  * **Open Web Image Filter API** -  Images filtered according to specific entities recognized within the image, or other valuable data such as GPS info, XMP, EXIF, and IPTC. 
  * **Archived Web Data** - Historical data from archived news, blogs, discussions and reviews going back more than 10 years.


In addition, we offer a** Open Web Firehose ** solution, which delivers data at scale from News, Blogs, Discussions and Reviews. Unlike the other APIs where the retrieved data is pre-filtered, the Firehose solution provides all the data we crawl. Posts are put in an XML format, compressed and uploaded in 10 megabytes Zip files, and made available to retrieve every other minute on a dedicated FTP site.

On the **Dark Web**, we provide access to data that is crawled and extracted from dark and deep networks and various messaging applications.

  * **Data Breach Detection API **- Leaked records from different dark web networks, sites, and applications from the last 5 years
  * **Cyber API **- Content from millions of illicit sites from multiple networks, such as TOR, I2P, Zeronet, Telegram, IRC and many others
  * **Image Filter API **- Images from marketplaces, discussions and social networks that visually represent potentially illicit products, services, expressions, opinions or actual GPS location  

Webhose.io supports both HTTP and HTTPS (SSL) endpoint calls.

**Authentication is confirmed via a unique Private Access Token passed in the API call URL. **

You can find your access token on your [dashboard ↗](https://webhose.io/dashboard) and you can also pick it up here, under each of the different Endpoints - 
Just make sure you're logged in first. 

All API plans include a unique access token, with a builtin rate limitation of 1 (one) request per second. 

{
  "type": "success",
  "title": "If you require higher rate, just [ let us know](https://webhose.io/talk-to-an-expert).<br>Webhose Data Consultants would love to talk to you!"
}



Webhose.io supports both HTTP and HTTPS (SSL) endpoint calls.

Authentication is confirmed via a unique Private Access Token passed in the API call URL. 

You can find your access token on your [dashboard ↗](https://webhose.io/dashboard) and you can also pick it up here, under each of the different Endpoints - 
Just make sure you're logged in first. 

**Webhose.io supports GET requests.**
Extremely long queries that exceed HTTP GET limitations, should be split into multiple, shorter requests.

**Webhose.io supports GET requests.**
Extremely long queries that exceed HTTP GET limitations, should be split into multiple, shorter requests.

**The URL query call has three parts:**


1.  The API endpoint (different for each API)

2.  The HTTP GET parameter string for authentication, time period, paging, and formatting

3.  The query string that passes the filter keys and value assignments to ensure that the API 
    retrieves precisely the data you need

Request method is HTTP GET.
[block:api-header]
{
  "title": "URL Structure"
}
[/block]

[block:html]
{
  "html": "<div>\n  <p>https://webhose.io/filterWebContent?token=xxxxx-xxxx-xxxxx&format=json&q=[QUERY]</p>\n</div>\n\n<style></style>"
}
[/block]

[block:html]
{
  "html": "<p class=\"mb-5\"></p>"
}
[/block]

[block:api-header]
{
  "title": "HTTP GET Parameters"
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Description",
    "h-2": "Example",
    "0-0": "q",
    "1-0": "token",
    "2-0": "sort",
    "3-0": "order",
    "4-0": "from",
    "5-0": "ts",
    "6-0": "format",
    "7-0": "size",
    "8-0": "accuracy_confidence",
    "9-0": "highlight",
    "10-0": "latest",
    "11-0": "warning",
    "0-1": "A Boolean query containing the filters that define which posts will be returned.",
    "0-2": "Find any post containing either ipod or ipad, but not android:\n\n(ipod OR ipad) -android",
    "1-1": "Your private access token that you received when you signed up.",
    "2-1": "When the sort parameter isn’t specified, the results are sorted by default in the recommended order of crawl date.\nYou can change the sort type by using the following values:\n\n\n   relevancy\n   social.facebook.likes\n   social.facebook.shares\n   social.facebook.comments\n   social.gplus.shares\n   social.pinterest.shares\n   social.linkedin.shares\n   social.stumbledupon.shares\n   social.vk.shares\n   replies_count\n   participants_count\n   spam_score\n   performance_score\n   published\n   thread.published\n   domain_rank\n   ord_in_thread\n   rating",
    "2-2": "&sort=relevancy",
    "3-1": "If you choose to order the posts by any of the above sort types, you can choose the sort order:\n\nAscending - asc (default)  \nDescending - desc",
    "3-2": "&sort=rating&order=desc",
    "4-1": "A paging parameter applicable for sort types other than crawl date.",
    "4-2": "&from=100",
    "5-1": "The **ts** (timestamp) parameter returns results that were crawled after this timestamp (**ts** is a Unix timestamp in milliseconds).\nHere is a [Timestamp/Date converter](https://www.epochconverter.com/)\n**When not specified the default is the past 3 days.**",
    "5-2": "&ts=1459835503426",
    "6-1": "The output format of the results set. It can be one of:\n\n  **json (default)**\n  **xml**\n  **rss **\n  **excel **",
    "6-2": "&format=xml",
    "7-1": "The number of posts returned per request. **size **may be between 1 and 100 (default is 100).",
    "7-2": "&size=2 \nWill return 2 posts",
    "8-1": "Return only posts with high extraction accuracy, but remove about 30% of the total matching posts (with lower confidence).",
    "8-2": "&accuracy_confidence=high",
    "9-1": "Return the fragments in the post that match the textual Boolean query. The matched keywords will be surrounded by <em/> tags.",
    "9-2": "&highlight=true",
    "10-1": "Return the latest 100 crawled posts matching your query. \n*Use of this feature is **NOT **recommended as it may result in loss of important posts.*",
    "10-2": "&latest=true",
    "11-1": "Warnings can arise from a malformed query parameter included in your code.\n\nIf set to **true**, then warning message details are included in the response under the **warnings** object.\n\nThe warning includes:  The message, its type and level.\n\nBy default warnings are disabled.",
    "11-2": "&warning=true"
  },
  "cols": 3,
  "rows": 12
}
[/block]

[block:html]
{
  "html": "<p class=\"mb-5\"></p>"
}
[/block]

