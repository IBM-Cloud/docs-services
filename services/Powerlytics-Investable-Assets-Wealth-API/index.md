---

copyright:

  years:  2018

lastupdated: "2018-11-20"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About Powerlytics Investable Assets & Wealth API
{: #gettingstarted}

The Powerlytics Investable Assets & Wealth API can be leveraged to understand the investable assets and wealth income at the 9-digit Zip code level (3-4 homes on average).  Our investable assets are segmented by size class with the number of returns within each segment and the average investable assets per segment.  In addition to leveraging our variables to understand the investable assets with a 9-digit Zip code, our customers can understand the wealth income (Interest Income + Dividend Income + Capital Gain or Loss) and Retirement Income for that same 9-digit Zip code in order to target investment and financial advisory services to customers that best meet their asset & wealth income thresholds.

{:shortdesc}

### Getting started

The Powerlytics' API is simple to use, it's a restful API that returns JSON.

Contact the Powerlytics sales team via phone: (215) 375-7675 Ext. 10 or email: sales@powerlytics.com to obtain a free evaluation API key

Once an API key has been obtained, all Powerlytics APIs may be accessed via http/https GET requests. API responses will be returned in JSON format.

------
### Using the API
#### GET ibm_siw_2017_v1
IBM Summary Income and W2 API with 2017 Data
#### Resource URL
`http://api-test.powerlytics.com/ibm_siw_2017_v1`
#### Resource Information
<table>
<tbody>
<tr>
<td width='50%'>
API version
</td>
<td width='50%'>
1
</td>
</tr>
<tr>
<td width='50%'>
Data source
</td>
<td width='50%'>
Consumer
</td>
</tr>
<tr>
<td width='50%'>
Geography fixed?
</td>
<td width='50%'>
No
</td>
</tr>
<tr>
<td width='50%'>
Size class fixed?
</td>
<td width='50%'>
No
</td>
</tr>
<tr>
<td width='50%'>
Organization type
</td>
<td width='50%'>
N/A
</td>
</tr>
<tr>
<td width='50%'>
Response format
</td>
<td width='50%'>
JSON
</td>
</tr>
<tr>
<td width='50%'>
Authentication required?
</td>
<td width='50%'>
API Key
</td>
</tr>
</tbody>
</table>

#### Fixed Parameters
These parameters and values are provided for informational purposes and
my not be changed.

|Name|Type|Depends On|Values|
|---|---|---|---|
|**year**<br>*Fixed*|Array of Ints||**Dependent Value:** None<br>**Default Value:** 2017<br>**Valid Value(s):** 2017|
|**geocol**<br>*Fixed*|String||**Dependent Value:** None<br>**Default Value:** zip9<br>**Valid Value(s):** zip9|

#### Settable Parameters
URL query parameters that are set for each API call.

|Name|Type|Depends On|Values|
|---|---|---|---|
|**key**<br>*required*|String||`<api key>`|
|**geoin**<br>*required*|Array of Strings|**geocol**|**Dependent Value:** zip9<br>**Default Value:** None<br>**Valid Value(s):** A single zip9 in the format 000000000.|

**NOTE:**
*For parameters that accept an array of values, the array is specified
as a coma separated list of values enclosed in quotes. Quotes should be
used even if a single value is being supplied.*
#### JSON Result Details
##### 'response' object attributes
##### data\_type
Type of data used for this API call. Either *'consumer'* or *'business'*
##### data\_level
Indicates the level of the Geography used in the results. When 'data rollup' occurs because insufficient data was available for the specified geography value(s), the data_level attribute specifies the geographic output level of the JSON results.

For example the following JSON, *{ "data\_level": "county" }* , would be interpreted to mean that the geographic level of the data is at the *county* level.

The following table lists the possible geographic values for the *data_level* value string:

|Geographic Values|
|---|
|county|
|msa|
|state|
|us|
|zipcode|
|zip9|

**NOTE:**
*Any combination of geographic and industry values may be returned in
the data\_level field value.*
#### Example Request
Test Server:<br>
`http://api-test.powerlytics.com/ibm_siw_2017_v1?key=<your_api_key>&geoin=085401050`
#### Example Request JSON Result
``` {.pre-scrollable}
{
  "report_results": {
    "name": "ibm_siw_2017_v1",
    "version": "1",
    "inputs": {
      "geoin": "085401050"
    },
    "response": {
      "data_type": "inc_score",
      "data_level": "zip9",
      "response_records": [
        {
          "taxyear": 2017,
          "geography": [
            {
              "zipcode": "08540",
              "cluster": "085401050",
              "zip_plus_4": "1050",
              "no_z4": 0,
              "county_name": "Mercer County",
              "msa_name": "Trenton, NJ Metro Area",
              "state_name": "New Jersey",
              "state_abbr": "NJ",
              "division": "Middle Atlantic Division",
              "region": "Northeast Region",
              "num_z4s_in_cluster": 4,
              "number_of_returns_in_cluster": 12,
              "cluster_total_wages_salaries_tips_w2": "3107.0701",
              "avg_wages_salaries_tips_w2": "258.9225",
              "adult_avg_wages_salaries_tips_w2": "155.3535",
              "cluster_total_household_income_excluding_schedule_e": "4748.9621",
              "avg_household_income_excluding_schedule_e": "395.7468",
              "adult_avg_household_income_excluding_schedule_e": "237.4481",
              "cluster_total_business_income_or_loss": "371.694",
              "avg_business_income_or_loss": "30.9745",
              "adult_avg_business_income_or_loss": "18.5847",
              "cluster_total_retirement_income": "747.121",
              "avg_retirement_income": "62.2601",
              "adult_avg_retirement_income": "37.3561",
              "cluster_total_disposable_income": "3013.8252",
              "avg_disposable_income": "251.1521",
              "adult_avg_disposable_income": "150.6913",
              "cluster_total_schedule_e_income": "1187.467",
              "avg_schedule_e_income": "98.9556",
              "adult_avg_schedule_e_income": "59.3734",
              "cluster_total_wealth_income": "3934.607",
              "avg_wealth_income": "327.8839",
              "adult_avg_wealth_income": "196.7303",
              "cluster_total_non_wage_income": "1588.4261",
              "avg_non_wage_income": "132.3688",
              "adult_avg_non_wage_income": "79.4213",
              "cluster_total_household_income_including_schedule_e": "5936.4292",
              "avg_household_income_including_schedule_e": "494.7024",
              "adult_avg_household_income_including_schedule_e": "296.8215",
              "cluster_standard_deviation_of_household_income": "64.93",
              "cluster_median_household_income": "280.75",
              "cluster_maximum_household_income": "412.27",
              "cluster_minimum_household_income": "119.158"
            }
          ]
        }
      ]
    }
  }
}
```
#### Request Errors
When API requests fail, an HTTP error code with a json data block in the
response body is returned.
##### HTTP Error 400 - Bad Request
##### Cause
One or more api call parameters are either missing or invalid.
##### Example JSON Response Body
``` {.pre-scrollable}
{
  "api_name": "ibm_siw_2017_v1",
  "version": 1,
  "msg": "Parameter error(s)",
  "errors": [
    {
      "name": "geoin",
      "status": "missing",
      "detail": "required"
    }
  ]
}
```
##### HTTP Error 401 - Unauthorized
##### Cause
The supplied API Key is invalid for the API call.
##### Example JSON Response Body
``` {.pre-scrollable}
{
  "status": "Invalid API key."
}
```
##### HTTP Error 404 - Not Found
##### Cause
The api name specified in the URL could not be found.
##### Example JSON Response Body
``` {.pre-scrollable}
{
  "status": "API not found"
}
```
#### Line Items Returned
|Name|Type|Scale|
|---|---|---|
|Wages, salaries, tips (W2)|Dollars|1000|
|Household income Excluding Schedule E|Dollars|1000|
|Business income or (loss)                |Dollars|1000|
|Retirement income                        |Dollars|1000|
|Disposable Income                        |Dollars|1000|
|Schedule E Income                        |Dollars|1000|
|Wealth income                            |Dollars|1000|
|Non Wage Income                          |Dollars|1000|
|Household Income Including Schedule E    |Dollars|1000|
|Standard Deviation of Household income   |Dollars|1000|
|Median household income                  |Dollars|1000|
|Maximum household income                 |Dollars|1000|
|Minimum household income                 |Dollars|1000|

Copyright ©2011-2018, Powerlytics, Inc. All rights reserved.
[Privacy Policy](http://api-test-con.powerlytics.com/privacy),
[Terms of Service](http://api-test-con.powerlytics.com/terms)