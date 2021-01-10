---

copyright:

  years:  

lastupdated: ""

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About 
{: #gettingstarted}

Firehose is an Enterprise-Level Data Feed that provides access to all the data Webhose crawls, from all territories in every language from Open Web verticals.

Unlike the other APIs where the retrieved data is pre-filtered, the Firehose solution provides all the data from News, Blogs, Discussions and Reviews. Posts are put in an XML format, compressed and uploaded in 10 megabytes Zip files, and made available to retrieve every other minute on a dedicated FTP site.

**Use Cases**
As organizations scale, they often need access to web data feeds at scale.
Webhose provides unfiltered data from all territories in all languages through our Firehose solution from Open Web verticals

Here are a few examples of how enterprise organizations are using Webhose’s firehose to scale their data:

**Financial analytics**
SESAMm, a fintech company that uses big data and artificial intelligence for investment, has incorporated Webhose’s alternative web data into their trading strategies to beat the market and enhance their signal. Increasing numbers of investment managers are using web data for different trading strategies, including predictive analytics applications, machine learning, and natural learning processing (NLP).


**Political analysis**
Buzzilla, a social media monitoring and analysis company, used Webhose’s data to compute Brand Positioning Index (BPI) scores that accurately predicted the outcome of the 2015 Israeli elections



{:shortdesc}

## Getting started

**Firehose Access and Data structure**
Your unique Firehose link enables unfiltered access to all crawled data for a given
vertical data feed - News, Blogs or Discussions.

The URL looks like this:
**feed.omgili.com/xxxxxxx/mainstream/**

The link points to a directory list of ZIP files capped at 10 MB and updated every other minute as newly crawled data becomes available.

Every compressed ZIP file contains a set of XML files - each of which corresponds to a single post.

Here's suggested pseudo-code for downloading Firehose Data

Set current_epoch_timestamp = get_currect_epoch_timestamp()
Read list of zip files from the firehose link
Download zip file and extract
Every 1 minute:
Read Firehose Link
For each zip file name(*):
    If Number(zip file name) > current_epoch_timestamp
        Download zip file


**Note:** Every Zip file name matches the file's creation timestamp

Since the crawlers are distributed and may not be in sync with each other, the
final duplication test is done by the firehose using the topic URL + number of
posts. If a post is added to a thread, all the posts of that thread will be
re-introduced to the firehose.
This can indeed cause an increased content duplication in the firehose, but in no way will it compromise the data integrity.

To ensure this, we have added the <seen_before>(True/False)</seen_before> field
to the Firehose output, which indicates whether a specific post was
previously sent out via the Firehose or not.
Sorting according to this field should ensure that you do not encounter duplicates.

We do our best to pick up unique posts' URLs from the pages we crawl, when possible. But sources don't always make those available, and sometimes there is no way to acquire unique URLs.
In such cases, we fabricate our own ID per post.
See the **<post_id>** field on the Firehose Output.

Please note that once we fabricate an ID, the post_url will not include it.

Ensure that you **concatenate the post_url + post_id**.
Only a combination of the **post_url and post_id** fields is considered a **unique post**.

| Field                | Type   | Description                                                                                                                                                                                                 | Details                                                                                                                                      |
|----------------------|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| type                 | String | Source type code name	                                                                                                                                                                                      | 	forums for Online-Discussions and Messaging Boards mainstream for News outlets blogs for, well Blogs                                        |
| forum                | String | URL of the section in the site where the thread was created	                                                                                                                                                |                                                                                                                                              |
| forum_title	         | String | Title of the section in the site where the thread was created	                                                                                                                                              |                                                                                                                                              |
| discussion_title     | String | Title of the thread	                                                                                                                                                                                        |                                                                                                                                              |
| language	            | String | Language in lower case e.g. “english", "spanish" etc	                                                                                                                                                       | The exception is "chineset" for Taiwanese Mandarin.                                                                                          |
| gmt_offset	          | Int    | Time difference between Jerusalem timezone and GMT	                                                                                                                                                         | GMT+02:00 / GMT+03:00 according to Jerusalem daylight savings                                                                                |
| topic_url            | String | Thread URL	                                                                                                                                                                                                 |                                                                                                                                              |
| topic_title          | String | Main post title	                                                                                                                                                                                            |                                                                                                                                              |
| topic_text	          | String | Main post text	                                                                                                                                                                                             | An empty text field is a valid value since a post could be made only from a title, or if the text field is made from emojis or images.       |
| spam_score	          | Float  | How 'spammy' a post is	                                                                                                                                                                                     | 0.0 through 1.0 where 1.0 means higher suspicion of spam                                                                                     |
| post_num             | Int    | Numbered order of post in the thread	                                                                                                                                                                       | The main post ID is 1. The first reply ID is 2 and so on.                                                                                    |
| post_id	             | String | Post ID	                                                                                                                                                                                                    | Typically, derived by truncating the post URL string to extract the anchor hashtag http://www...#post-ID                                     |
| post_url             | String | Post URL	                                                                                                                                                                                                   | Typically, topic_url followed by #post-ID. To avoid duplication, you should always make sure post_url is followed by the above post_id       |
| post_date	           | String | Date in YYYYMMDD format	                                                                                                                                                                                    |                                                                                                                                              |
| post_time            | String | Time                                                                                                                                                                                                        | GMT+02:00 / GMT+03:00 according to Jerusalem daylight savings                                                                                |
| username             | String | Author name	                                                                                                                                                                                                |                                                                                                                                              |
| post_title           | String | Post title	                                                                                                                                                                                                 |                                                                                                                                              |
| post                 | String | Post content	                                                                                                                                                                                               | Note, an empty text field is a valid value since a post could be made only from a title, or if the text field is made from emojis or images. |
| signature            | String | Author's closing message	                                                                                                                                                                                   |                                                                                                                                              |
| external_links	      | String | external_links                                                                                                                                                                                              |                                                                                                                                              |
| country              | String | 2 letter ISO country code	                                                                                                                                                                                  |                                                                                                                                              |
| main_image	          | String | URL of image	                                                                                                                                                                                               |                                                                                                                                              |
| rating               | Float  | Rating                                                                                                                                                                                                      | Discussions that include 1 through 5 Ratings                                                                                                 |
| is_lang_certain      | Bool   | Detected language certainty	                                                                                                                                                                                |                                                                                                                                              |
| seen_before	         | Bool   | True if the post is newly-crawled or false if seen before on a thread	                                                                                                                                      |                                                                                                                                              |
| accuracy_confidence	 | Bool   | Data extraction accuracy	                                                                                                                                                                                   |                                                                                                                                              |
| domain_rank	         | Int    | Domain rank	                                                                                                                                                                                                |                                                                                                                                              |
| site_categories	     | String | Category                                                                                                                                                                                                    |                                                                                                                                              |
| reviewed_url         | String | Contains the URL of the reviewed entity	                                                                                                                                                                    | Exists only in the reviews feed. In most cases the reviewed_url will be the same as the topic_url without the anchor fragment.               |
| entities             | String | persons - a list of identified people names found in the post  locations - a list of identified locations found in the post  organizations - a list of identified companies/organizations found in the post | Currently available for news and blogs posts in English (excluding the comments)                                                             |

