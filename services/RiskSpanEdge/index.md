---

copyright:

  years:  2017

lastupdated: "2017-03-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with RiskSpanEdge
{: #gettingstarted_RiskSpanEdge}

RS Edge is a data discovery and modeling tool which prrovides access to billions of rows of mortgage performance data.  Our proprietary search and retrieval technology and scalable back-end data center allows for fast querying and ad-hoc analysis on-demand. Analysis is combined with RiskSpan's proprietary projection models to enable forecasting of credit and prepayment performance.
{:shortdesc}


RS Edge provides a REST API to the data and analytic engine. To integrate your app with the service, complete these steps: 
1. Obtain auth ID from RiskSpan
2. Create a bucketing criteria appropriate to your analysis
3. Select the required stress scenario.


## REST API parameters

* auth_key - your key for accessing the RS Edge API
* deal_name - name of the portfolio being analyzed (Please use the sample portfolio: ABANK)
* trade_date - analysis date (YYYYMMDD format, example 2015 
* bucket_key - RS Edge XML query format
* scenario specification


## Output

Output from the API is generated in JSON format. The output consists of:
* user defined data clusters
* user defined loan performance aggregates
* model performance including defaults and loss given defaults


## Sample call

```
curl 
-H "Accept:application/json" 
"http://uat.riskspan.com:18080/RSEdgeRest/EdgeRestService?deal_name=_ABANK&trade_date=20170306&
auth_key=X&
bucket_file=%3CNewBucketingFile%3E%3CDataset%20Value=%22_ABANK%22%20/%3E%
3CBucket%20Type=%22FactorDate%22%20Min=%2220150301%22%20Max=%2220150301%22%/%3E%
3CBucket%20Type=%22property_type%22%20Value=%22Condo~MH~PUD~SF~Townhouse%22/%3E%3C/NewBucketingFile%3E"
```
{: codeblock}


## Sample output

```
[
{"TotalLoss24":5597.6096912743,"ClusterName":"property_type_Bucket:CoOp;FactorDate_Bucket:20150301",
"TotalDefault24":28972.4729673213,"FactorDate":20150301},
{"TotalLoss24":1141830.3249466524,"ClusterName":"property_type_Bucket:Condo;FactorDate_Bucket:20150301",
"TotalDefault24":5239660.846315403,"FactorDate":20150301},
{"TotalLoss24":2633.9005572687,"ClusterName":"property_type_Bucket:Lease;FactorDate_Bucket:20150301",
"TotalDefault24":14105.2054139588,"FactorDate":20150301},
{"TotalLoss24":2910363.9010554748,"ClusterName":"property_type_Bucket:PUD;FactorDate_Bucket:20150301",
"TotalDefault24":1.049387823253114E7,"FactorDate":20150301},
{"TotalLoss24":19602355.4886333,"ClusterName":"property_type_Bucket:SF;FactorDate_Bucket:20150301",
"TotalDefault24":7.659159340336753E7,"FactorDate":20150301},
{"TotalLoss24":16602.2375726766,"ClusterName":"property_type_Bucket:Townhouse;FactorDate_Bucket:20150301",
"TotalDefault24":60480.4719230693,"FactorDate":20150301}
]
```
{: screen}


# Related Links
{: #rellinks notoc}

## API Reference
{: #api}

*  https://riskspan.com/s/rs-edge-api.pdf


## Related Links
{: #general}

* RS Edge: https://www.riskspan.com/rs-edge
* Contact RiskSpan: https://www.riskspan.com/contact-us
* Terms and conditions: https://riskspan.com/s/rs-edge-terms-and-conditions.pdf
