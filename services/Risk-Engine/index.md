---

copyright:

years:  2018:

lastupdated: "2018-07-17"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# AboutRisk Engine
{: #gettingstarted}

The dacadoo Risk Engine calculates health-related mortalilty and disease risks such as all-cause mortality and Diabetes type II. The calculation is based on numerous biometric inputs, such as height, weight, blood pressure, heart rate, blood values, and questionnaire responses. Only sex, age, height and weight are required. Other missing values can be imputed by the engine. In addition to the resulting risks, the engine returns the fully imputed input data set.

{:shortdesc}

## Getting started

To get started, you need to request an [API key](https://models.dacadoo.com/doc/key). An evaluation key is provided immediately and free of charge after completing a short request form.

Send a request to the risk engine API endpoint as follows:

```
POST /risk/1 HTTP/1.1
Host: models.dacadoo.com
X-dacadoo-Key: <API key>
Content-Type: application/json; charset=UTF-8

{
  "years": 10,
  "mhm": {
    "age": 40,
    "height": 180,
    "sex": 0,
    "weight": 0
  },
  "smk": {
    "now": 0,
    "evr": 0
  }
}
```

You need to replace `<API key>` with your actual API key, omitting the angular brackets.

Please refer to the [API Documentation](https://models.dacadoo.com/risk/) to learn about the complete set of biometric inputs you can pass in the request. The above example represents a small subset of the input domain.

The API will respond as follows:

```
200 OK
Content-Type: application/json; charset=UTF-8
X-dacadoo-Quota: interval=minute; count=1; limit=50; next=1530008580, interval=day; count=1; limit=10000; next=1530057600

{
  "years": 10,
  "risks": {
    "mrt": {
      "abs": 0.106,
      "rel": -0.090
    },
    ...
  },
  "mhm": {
    "age": 40,
    "height": 180,
    "sex": 0,
    "weight": 0,
    "sbp": 123.37218893241,
    "dbp": 77.882899532576,
    "fbg": 5.156689400265,
    ...
  }
}
```

Again, please refer to the [API Documentation](https://models.dacadoo.com/risk/) to learn about the complete set of health risks and imputed values returned by the risk engine. The above example represents a small subset of the output domain.

