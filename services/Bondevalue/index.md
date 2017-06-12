---

copyright:

  years:  2017

lastupdated: "2017-06-01"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with BondEvalue API
{: #gettingstarted_Bondevalue}

BondEvalue provides you access to live and historical bond prices and yields data for bonds. Unlike
equities which have already been digitally disrupted, bonds have remained unchanged for decades,
with private bank clients unable to access live prices
With the help of our advanced algorithm we monitor the bond specific data points from a large
variety of sources and enable individual investors to get the latest and accurate bond prices, yields,
liquidity, riskiness, news and many other data points which help them to make more informed
decisions at the time of bond trading.
{:shortdesc}

<!-- If overview content is required, do not include it here. Put it in a separate "## About" section below the task section. -->

<!-- Task section: REQUIRED
The task section includes steps to integrate the service into the app.  
- With task-based, technical information, reduce the conversational style in favor of succinct and direct instructions.
- DO include the basic, most-common-use scenario steps to use the service or integrate it into the app. 
- DO NOT include steps to add the service from the Bluemix catalog; we assume that the user already took steps in the UI to add the service. 
- DO include code snippets in all languages that can be copied, as well as VCAP service info.  
- For additional tasks like configuring, managing, etc., add a task section (## Gerund_task_title) below the task section or "About" section if used. Use a task title such as "Configuring x", "Administering y", "Managing z". -->

<!-- You can include an optional prerequisites paragraph for any prerequisites to be met before integrating the service. For example: -->

## Viewing the API data

You need to follow the below mentioned steps to gain access for viewing the real time and historical bond data points.

- Create and Login to your account on [Bondevalue](https://bondevalue.com/app/userRegisteration){:new_window}.
- From the dropdown menu in the top-left corner of the page, click on the “Daily Price API data” and “Historical Price API data” option to view the daily and historical bond prices respectively.

## Daily Price API Data

JSON Format
	
	```json
	{
	"country": "CHN",
	"callable": "Yes",
	"issuerNameInBoldLetters": "361 Degrees",
	"ISINCode": "XS1415758991",
	"bondPrice": "108.188",
	"YieldChangeInBpUnit": "-2",
	"rating": "Medium",
	"currentDate": "31-May-2017 14:47:00",
	"bondMaturityDate": "06/21",
	"perpetual": "No",
	"countryOfRisk": "CHN",
	"currencyName": "United States dollar",
	"currency": "USD",
	"priceChangeInPercentage": "0",
	"previousDate": "24-May-2017 16:24:00",
	"priceChange": "0",
	"bondCoupon": "7.25",
	"yieldChangeInPercentage": "-0.37",
	"maturityYrsRemain": "4",
	"bondAmountOut": "400000000",
	"bondYield": "4.67",
	"issuerNameInNormalLetters": "International Ltd",
	"countryName": "China",
	"yieldChange": "-0.02",
	"countryOfRiskName": "China"
	}
	```
	{: codeblock}
<!-- Include a sentence to briefly introduce the steps. Examples: -->

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->
 
API Field Name      | Description
--------------------|------------
"callable"	    | Provides the value if the bond is callable or not.
"ISINCode"          | Filters documents by the index, see below table for supported indexes. To filter by multiple indexes pass a comma separated list of indexes.
"bondPrice"         | The current price of the bond.
"YieldChangeInBpUnit"	|	The daily yield change value is terms of basis points system.
"rating"		|Information about the riskiness of the bond.
"bondMaturityDate"	|Information about the maturity date of the bond
"perpetual"	|Value if the bond is Perpetual or not.
"currencyName"	|Information about the bond currency.
"bondCoupon"	|Value of the bond coupon.
"maturityYrsRemain" | The number of years left for bond’s maturity
"bondAmountOut"  | Total outstanding amount for the bond.
"bondYield" |Current bond yield.
"issuerNameInNormalLetters" | Name of the bond Issuer
"countryOfRiskName"	|Bond’s country of risk

## Historical Price API Data

JSON Format
	
	```json
	{
 	"ISINSDetailMap": {
	 "IssuerISINId": "77",
 	"bondCoupon": "2.75",
 	"bondISIN": "XS1209864229"
	 },
	 "bondDetailsGraphDataList": [
 	{
 	"UIFormattedDate": "Wed,Dec 07",
 	"bondPrice": "99.326",
 	"day_of_year": "342",
	 "year": "2016",
 	"month_of_year": "12",
 	"day_of_month": "7",
 	"bondYield": "2.96",
 	"month": "December",
 	"bondDataUpdateDate": "2016-12-07",
 	"day": "Wednesday",
 	"week_of_year": "49",
	 "day_of_week": "4"
 	},
 	{
 	"UIFormattedDate": "Thu,Dec 08",
 	"bondPrice": "99.447",
 	"day_of_year": "343",
	 "year": "2016",
 	"month_of_year": "12",
 	"day_of_month": "8",
 	"bondYield": "2.93",
 	"month": "December",
 	"bondDataUpdateDate": "2016-12-08",
 	"day": "Thursday",
 	"week_of_year": "49",
 	"day_of_week": "5"
 	}
	```
	{: codeblock}
	
API Field   | Name Description
------------|------------
"bondCoupon" |Value of the bond coupon.
"bondISIN"   |Provides the unique ISIN value of the bond for which the historical data is being shown.
"UIFormattedDate" |The date for which the data is being shown.
"bondPrice" |The price of the bond for the mentioned date.
"bondYield" |The yield of the bond for the mentioned date.	

## Using BondEvalue APIs

You need an API access token to receive data from BondEvalue APIs. To request an API access token,
please follow the steps below:

- Register and login to your account on Bondevalue
- From the dropdown menu in the top-left corner of the page, click on the “Instructions to use API” option as shown below.
- Once the link is clicked you will be provided with a 16-character token which is required to access the APIs.

## Using the Daily Price API

- Request URL : https://bondevalue.com/app/bondsDataDailyChange
- Request Method : POST
- Request Content-Type : application/x-www-form-urlencoded
- Request Parameter : requestData = "{\"data\":{\"userToken\":\"[userToken]\"}}" 
- [Note: The requestData will be encrypted by an encryption algorithm]

In order to encrypt the request parameter, the developer needs to follow the following steps:

- Encryption Algorithm Used: ALGO = "AES/ECB/PKCS5Padding";
- The encryption algorithm uses AES 128 method where the 16-character token provided will act as the 128 bits key to encrypt.

### Example

- Before Encryption Data : requestData:{"data":{"userToken":"slabnt1l540udrh0"}}
- After Encryption Data : requestData: ylwciqc9e2E4kwYCRRsAvUcQlQ7cn23QMO22i+9FH/3iinCQItonOgAW3EHok6Fv

## Using the History Price Data API

- Request URL : https://bondevalue.com/app/bondDetailsHistoryData
- Request Method : POST
- Request Content-Type : application/x-www-form-urlencoded
- Request Parameter : requestData = "{\"data\":{\"userToken\":\"[userToken]\"},\"bondISINId\":\"[isinId]"\"" "\"fromDate\":\"[from date]\" "}"
- [Note: The requestData will be encrypted by a encryption algorithm]

In order to encrypt the request parameter, the developer needs to follow the following steps:

- Encryption Algorithm Used: ALGO = "AES/ECB/PKCS5Padding";
- The encryption algorithm uses AES 128 method where the 16-character token provided will act as the 128 bits key to encrypt.

### Example

- Before Encryption Data : requestData = {"data":{"userToken":"slabnt1l540udrh0"},"bondISINCode":"XS1401197253" "fromDate":""}
- After Encryption Data : requestData = ylwciqc9e2E4kwYCRRsAvUcQlQ7cn23QMO22i+9FH/3n4peo+9dm7XMnNSx3E45WZiNEUsepGQNHED2kzqKporz5bQTOzP8i/tD57OCE7kUr5EIeaqk8OKzmHu8KeQAM
- Note: This particular API requires the bond ‘s ISIN Id and the from date to view the history data for that particular ISIN ID. 

## Support

In case you are unable to access the APIs or are having issues with user registration on the webpage,
kindly contact bondevalue@bondevalue.com


<!-- Related links section: REQUIRED but moved to toc file (in your same folder).  Edit there by adding the following:

{: .navgroup id="learn"}
    index.md

    {: .topicgroup}
    Related links
        [Link text](URL)
    {: .navgroup-end}

To add related links, indent the 8 spaces, put the name of the link in [] and the URL in (), like so:
        [Link text](https://pathtolink.html)
    
If you have API references to add, leave a blank line under the previous navgroup and then add:

    {: .navgroup id="reference"}
    Reference
        [API Documentation](https://pathtolink.html)
    {: .navgroup-end}
-->
