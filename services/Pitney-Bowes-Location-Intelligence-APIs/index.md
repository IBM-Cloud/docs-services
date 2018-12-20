---

copyright:

  years:  2018

lastupdated: "2018-12-20"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About Pitney Bowes Location Intelligence APIs
{: #gettingstarted}

Transform location and business data into powerful insights.

{:shortdesc}

## Getting started

Please follow these steps to get started.

Register for a Pitney Bowes Developer Account. No credit card required.

After login, you will see your API key and secret listed on API Keys Page.

Note: Upon obtaining your credentials (API Key & Secret), you can use the credentials to generate an OAuth token and pass the OAuth token and pass the token in SDK and REST implementation to get the access.

To generate the OAuth Token, encode your credentials (API Key & Secret) using base64 computation mechanism. To do this, Provide your API key and Secret to the base64 encoder (online encoder can be used), and generate the encoded 'base64value'.

The following format is to be used while computing the {base64Value}:

{YOUR API KEY}:{YOUR SECRET}

where,

{YOUR API KEY}= API key obtained from developer's site

{YOUR SECRET}= Secret obtained from developer's site

***Note: In case of GeoMap API skip Step3, Step 4 and Step 5, as the API KEY is directly passed in this URL http://api.pitneybowes.com/location-intelligence/geomap/v1/tile/osm/{z}/{x}/{y}.png?api_key={YOUR API KEY}&theme=iron***


Authorization: Basic {base64Value}
Content-Type: application/x-www-form-urlencoded
POST https://api.pitneybowes.com/oauth/token
grant_type=client_credentials

{
"access_token": "{YOUR ACCESS TOKEN}"
"tokenType": "BearerToken",
"issuedAt": "1429188455329",
"expiresIn": "35999",
"clientID": "{YOUR API KEY}",
"org": "api.pitneybowes.com"
}

You can pass the token in SDK(Refer Locate SDKs to access SDK documentation) and REST implementations (example shown below).

Authorization: Bearer {YOUR ACCESS TOKEN}
GET http://api.pitneybowes.com/location-intelligence/geosearch/v1/locations?latitude={YOUR_LATITUDE}&longitude={YOUR_LONGITUDE}&searchText={YOUR_SEARCH_TEXT}

