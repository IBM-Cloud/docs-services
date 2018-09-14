---

copyright:

  years:  2018

lastupdated: "2018-09-07"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About Health Score
{: #gettingstarted}

The Health Score is a number between 0 and 1,000 representing the overall health of a person. The score is based on numerous biometric, lifestyle and psychometric inputs supporting a 360° view of human health. The score is normalized by age and sex to support comparison and benchmarking.

{:shortdesc}

## Getting started

To get started, you need to request an [API key](https://models.dacadoo.com/doc/key). An evaluation key is provided immediately and free of charge after completing a short request form.

Send a request to the health score API endpoint as follows:

```
POST /health/1 HTTP/1.1
Host: models.dacadoo.com
X-dacadoo-Key: <API key>
Content-Type: application/json; charset=UTF-8

{
  "mhm": {
    "age": 40,
    "sex": 0,
    "hgt": 180,
    "wgt": 70
  },
  "smk": {
    "now": 0,
    "evr": 0
  },
  "slp": {
    "bed": [ 8.0, null, null, 7.5, 8.0 ],
    "slp": [ 7.0, null, null, 5.0, 7.9 ],
    "awk": [ 2, null, null, 4, 1 ]
  },
  "nut": {
    "nqs": [ 0.5, 0.5, null, 0.5, null, null, 0.8 ]
  },
  "qlm": {
    "q01": 0.1,
    "q07": 0.7
  }
}
```

You need to replace `<API key>` with your actual API key, omitting the angular brackets.

Please refer to the [API Documentation](https://models.dacadoo.com/doc/score/) to learn about the complete set of biometric, lifestyle, and psychometric inputs you can pass in the request. The above example represents a small subset of the input domain.

The API will respond as follows:

```
200 OK
Content-Type: application/json; charset=UTF-8
X-dacadoo-Quota: interval=minute; count=1; limit=50; next=1530008580, interval=day; count=1; limit=10000; next=1530057600

{
	"scr": 718,
	"lcl": 137,
	"ucl": 73
	"rqy": 3.07766126409,
	"components": {
		"lfs": 690,
		"bdy": 827,
		"fee": 509
	},
	"subscores": {
		"mvm": 317,
		"nut": 550,
		"smk": 1000,
		"obe": 942,
		"slp": 514,
		"dep": 555,
		"wel": 570,
		"str": 553
	}
}
```

Again, please refer to the [API Documentation](https://models.dacadoo.com/doc/score/) to learn about the meaning of the returned values.

