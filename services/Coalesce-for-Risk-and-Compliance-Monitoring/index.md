---

copyright:

  years:  2017

lastupdated: "2017-11-21"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}


# Getting Started with Coalesce.Info for Risk Analysis
{: #gettingstarted_coalesce}

Investment managers and risk and compliance professionals use a wide variety of tools to understand the risks inherent in their investments. Coalesce is a unique Artificial Intelligence product that uses IBM Watson® to allow analysts and business users to search the internet and all forms of internal data for “Signals” that may be relevant to risk analysis.


To learn more about Coalesce.Info, visit our [website](http://coalesce.info/){:new_window}.

To start using Coalesce.Info, please first sign up for an account. Click [here](https://v2-0.coalesce.info/html/index.html#/signup){:new_window} to get started!

Once you've signed up to use Coalesce.Info, there are a few easy steps to go live.

1.  [Log-in](https://v2-0.coalesce.info/html/index.html#/login){:new_window} into the Coalesce.Info with the credentials used for signup to view news alerts for the sample Fortune 500 companies.
  
2.	Copy your Coalesce username / password credentials into the IBM Cloud developer portal (Note: Never share your credentials outside of the IBM cloud developer portal!)

3.	Use the Coalesce.Info API for real-time access (requires subscription) 

Coalesce.Info is free for 7 days. After that you will need to subscribe for continued access.

## API access 

To access the Coalesce APIs, a valid sessionId is necessary. To generate the sessionId one should have the valid username and password credentials.

You can use the same username / password used for Signup or Contact the support team to create username and password for you.

By default the response from the API feed is in JSON format.

## Authentication

Follow the steps to create the sessionId:

     URI : https://v2-0.coalesce.info/login.json
     
     Method : GET
     
1.	Concatenate the username and password with the separator ‘:’ and without space.
2.	Then use a function to encode the string to base64 ASCII String.
3.	Then Append ‘Basic <base64 String>‘ to the encoded string.
4.	Then add a request header with the key ‘Authorization’ and the generated string in the previous step as the value.
5.	Once it is successfully authenticated, the response body has the sessionId.
6.	To access the rest of the API endpoints, set a request header as Cookie and then prepend the string ‘JSESSIONID=’ to the sessionId and set it as value.

Shell
```shell
curl --basic --user username:password "https://v2-0.coalesce.info/login.json"
```
{: codeblock}


Python
```python
import requests, base64

url = "https://v2-0.coalesce.info/login.json"
base64string = base64.encodestring('%s:%s' % (username,password))
req.add_header("Authorization", "Basic %s" % base64string)
req = requests.get(url)
text_response = req.text # read response as Text
print(text_response)

json_response = req.json() # read response as JSON
print(json_response)
```
{: codeblock}

JavaScript
```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://v2-0.coalesce.info/login.json", true);
xhr.withCredentials = true;
xhr.setRequestHeader("Authorization", 'Basic ' + btoa('username:password'));
xhr.onload = function () {
    console.log(xhr.responseText);
};
xhr.send();
```
{: codeblock}

Java
```java
import java.io.BufferedReader;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.Base64;


public class HttpBasicAuth {

    public static void main(String[] args) {

        try {
            URL url = new URL ("https://v2-0.coalesce.info/login.json");
            String encoding = Base64.getEncoder().encodeToString(("username:password").getBytes("UTF-8"));

            HttpURLConnection connection = (HttpURLConnection) url.openConnection();
            connection.setRequestMethod("GET");
            connection.setDoOutput(true);
            connection.setRequestProperty  ("Authorization", "Basic " + encoding);
            InputStream content = (InputStream)connection.getInputStream();
            BufferedReader in = new BufferedReader (new InputStreamReader (content));
            String line;
            while ((line = in.readLine()) != null) {
                System.out.println(line);
            }
        } catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```
{: codeblock}

## Entites

`GET https://v2-0.coalesce.info/entities`

By default this request will return the first 1000 entities.

Shell
```shell
curl --cookie JSESSIONID=XXXXsessionIdXXXXX "https://v2-0.coalesce.info/entities"
```
{: codeblock}

Python
```python
import requests

url = "https://v2-0.coalesce.info/entities"
req.add_header("cookie", "JSESSIONID=XXXXsessionIdXXXXX")
req = requests.get(url)
text_response = req.text # read response as Text
print(text_response)

json_response = req.json() # read response as JSON
print(json_response)
```
{: codeblock}

JavaScript
```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://v2-0.coalesce.info/entities", true);
xhr.withCredentials = true;
xhr.setRequestHeader("cookie", "JSESSIONID=XXXXsessionIdXXXXX");
xhr.onload = function () {
    console.log(xhr.responseText);
};
xhr.send();
```
{: codeblock}

Java
```java
import java.io.BufferedReader;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.Base64;


public class EntitiesSearch {

    public static void main(String[] args) {

        try {
            URL url = new URL ("https://v2-0.coalesce.info/entities");
          
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();
            connection.setRequestMethod("GET");
            connection.setDoOutput(true);
            connection.setRequestProperty  ("cookie", "JSESSIONID=XXXXsessionIdXXXXX");
            InputStream content = (InputStream)connection.getInputStream();
            BufferedReader in = new BufferedReader (new InputStreamReader (content));
            String line;
            while ((line = in.readLine()) != null) {
                System.out.println(line);
            }
        } catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```
{: codeblock}


> The above url returns the most recent 100 documents.

JSON Format
```json
[
  {
    "id": 1,
    "name": "BASF",
    "website": "https://www.basf.com",
    "owner": "IBM Demo",
    "country": "United States of America",
    "descriptions": "At BASF, we create chemistry for a sustainable future. We combine economic success with environmental protection and social responsibility. The approximately 112,000 employees in the BASF Group work on contributing to the success of our customers in nearly all sectors and almost every country in the world. Our portfolio is organized into five segments: Chemicals, Performance Products, Functional Materials & Solutions, Agricultural Solutions and Oil & Gas. BASF generated sales of more than €70 billion in 2015. BASF shares are traded on the stock exchanges in Frankfurt (BAS), London (BFA) and Zurich (AN).\nCredits: https://www.basf.com/en/tools/legal/credits.html.",
    "sector": "Chemicals",
    "status": "Portfolio Company",
    "customId": "0017126318DB530204A9698F4D2DCF1D",
    "aliasName": "basf",
    "isActive": true,
    "createdBy": "demo",
    "createdTime": "2017-01-24 11:46:58"
  }
]
```
{: codeblock}

## Filtering

Parameter | Description
-----------| ------------
start	     | Filters entities by the index.
count      | Number of entities to be returned to a maximum of 1000 count.
active     | Filters documents by active flag.

### Filter by start, count, active

Shell
```shell
curl --cookie JSESSIONID=XXXXsessionIdXXXXX "https://v2-0.coalesce.info/entities?start=200&count=100&active=true"
```
{: codeblock}

Python
```python
import requests

url = "https://v2-0.coalesce.info/entities?start=200&count=100&active=true"
req.add_header("cookie", "JSESSIONID=XXXXsessionIdXXXXX")
req = requests.get(url)
text_response = req.text # read response as Text
print(text_response)

json_response = req.json() # read response as JSON
print(json_response)
```
{: codeblock}

JavaScript
```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://v2-0.coalesce.info/entities?start=200&count=100&active=true", true);
xhr.withCredentials = true;
xhr.setRequestHeader("cookie", "JSESSIONID=XXXXsessionIdXXXXX");
xhr.onload = function () {
    console.log(xhr.responseText);
};
xhr.send();
```
{: codeblock}

Java
```java
import java.io.BufferedReader;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.Base64;


public class HttpBasicAuth {

    public static void main(String[] args) {

        try {
            URL url = new URL ("https://v2-0.coalesce.info/entities?start=200&count=100&active=true");
          
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();
            connection.setRequestMethod("GET");
            connection.setDoOutput(true);
            connection.setRequestProperty  ("cookie", "JSESSIONID=XXXXsessionIdXXXXX");
            InputStream content = (InputStream)connection.getInputStream();
            BufferedReader in = new BufferedReader (new InputStreamReader (content));
            String line;
            while ((line = in.readLine()) != null) {
                System.out.println(line);
            }
        } catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```
{: codeblock}


## Alerts

`GET https://v2-0.coalesce.info/alerts`

By default, this request will return all the user created alerts associated to the user.

Shell
```shell
curl --cookie JSESSIONID=XXXXsessionIdXXXXX "https://v2-0.coalesce.info/alerts"
```
{: codeblock}

Python
```python
import requests

url = "https://v2-0.coalesce.info/alerts"
req.add_header("cookie", "JSESSIONID=XXXXsessionIdXXXXX")
req = requests.get(url)
text_response = req.text # read response as Text
print(text_response)

json_response = req.json() # read response as JSON
print(json_response)
```
{: codeblock}

JavaScript
```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://v2-0.coalesce.info/alerts", true);
xhr.withCredentials = true;
xhr.setRequestHeader("cookie", "JSESSIONID=XXXXsessionIdXXXXX");
xhr.onload = function () {
    console.log(xhr.responseText);
};
xhr.send();
```
{: codeblock}

Java
```java
import java.io.BufferedReader;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.Base64;


public class Alerts {

    public static void main(String[] args) {

        try {
            URL url = new URL ("https://v2-0.coalesce.info/alerts");
          
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();
            connection.setRequestMethod("GET");
            connection.setDoOutput(true);
            connection.setRequestProperty  ("cookie", "JSESSIONID=XXXXsessionIdXXXXX");
            InputStream content = (InputStream)connection.getInputStream();
            BufferedReader in = new BufferedReader (new InputStreamReader (content));
            String line;
            while ((line = in.readLine()) != null) {
                System.out.println(line);
            }
        } catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```
{: codeblock}

JSON Format
```json
[
  {
    "id": 1,
    "userId": 1,
    "name": "LEGAL ISSUES",
    "source": {
      "name": "News and Press",
      "id": 2,
      "displayName": "News and Press"
    },
    "keywordsExclude": null,
    "keywordsInclude": "Litigation, breach, fraud, sanction, penalty, accusation, investigation, convicted, lawsuit, alleged, guilty, probe, settle, violation",
    "threshold": 50,
    "rows": 10,
    "visibilityCategory": {
      "id": 4,
      "visibilityName": "USER"
    }
  }
]
```
{: codeblock}


## Alerts-Search

`GET https://v2-0.coalesce.info/alerts/alert/search?id=xxx`

By default this request will return all the alerts that has been generated by the system based on the user associated alerts.

Shell
```shell
curl --cookie JSESSIONID=XXXXsessionIdXXXXX "https://v2-0.coalesce.info/alerts/alert/search?id=xxx"
```
{: codeblock}

Python
```python
import requests

url = "https://v2-0.coalesce.info/alerts/alert/search?id=xxx"
req.add_header("cookie", "JSESSIONID=XXXXsessionIdXXXXX")
req = requests.get(url)
text_response = req.text # read response as Text
print(text_response)

json_response = req.json() # read response as JSON
print(json_response)
```
{: codeblock}

JavaScript
```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://v2-0.coalesce.info/alerts/alert/search?id=xxx", true);
xhr.withCredentials = true;
xhr.setRequestHeader("cookie", "JSESSIONID=XXXXsessionIdXXXXX");
xhr.onload = function () {
    console.log(xhr.responseText);
};
xhr.send();
```
{: codeblock}

Java
```java
import java.io.BufferedReader;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.Base64;


public class AlertsSearch {

    public static void main(String[] args) {

        try {
            URL url = new URL ("https://v2-0.coalesce.info/alerts/alert/search?id=xxx");
          
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();
            connection.setRequestMethod("GET");
            connection.setDoOutput(true);
            connection.setRequestProperty  ("cookie", "JSESSIONID=XXXXsessionIdXXXXX");
            InputStream content = (InputStream)connection.getInputStream();
            BufferedReader in = new BufferedReader (new InputStreamReader (content));
            String line;
            while ((line = in.readLine()) != null) {
                System.out.println(line);
            }
        } catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```
{: codeblock}

JSON Format
```json
[
  {
    "id": 1,
    "companyId": 1,
    "alertId": 1,
    "alertName": "LEGAL ISSUES",
    "title": "Lawyer Discusses Possible Dicamba Lawsuits Against Monsanto, BASF",
    "url": "https://www.agweb.com/article/lawyer-discusses-possible-dicamba-lawsuits-against-monsanto-basf-naa-ashley-davenport/",
    "publishedDate": "09/22/2017",
    "count": 1,
    "paragraphDTOList": [
      {
        "index": 0,
        "score": 0.53,
        "highlight": 1,
        "paragraph": "Lawyer Discusses Possible Dicamba Lawsuits Against Monsanto, BASF"
      },
      {
        "index": 1,
        "score": 0.61,
        "highlight": 0,
        "paragraph": "Farmers in at least 10 states have filed complaints against Monsanto and BASF claiming various levels of loss and crop damage due to dicamba-tolerant technology."
      },
      {
        "index": 2,
        "score": 0.53,
        "highlight": 0,
        "paragraph": "Farmers say the chemistry caused damage by drifting away from where it was intended to go, and damaged crops and trees that couldn’t tolerate it."
      },
      {
        "index": 3,
        "score": -0.6,
        "highlight": 0,
        "paragraph": "As farmers accuse the companies of negligence, the number of lawsuits are expected to climb, but it can be difficult to prove because of the companies they’re up against."
      },
      {
        "index": 4,
        "score": 0.59,
        "highlight": 0,
        "paragraph": "“Normally in a lawsuit over negligence, you would sue the person who causes the negligence,” said Todd Janzen, president of Janzen Agricultural Law LLC .. “In this case, that would be the applicator, but the lawsuit is against the company that put the product, which is dicamba, into the stream of commerce.”"
      },
      {
        "index": 5,
        "score": -0.56,
        "highlight": 0,
        "paragraph": "Janzen doesn’t represent any of the plaintiffs. He expects dicamba will remain on the market, but there’ll be additional restrictions."
      },
      {
        "index": 6,
        "score": 0.52,
        "highlight": 0,
        "paragraph": "Monsanto and BASF, who developed dicamba products, have been vocal to their opposition to the ban, calling it a “major step backwards” for farmers."
      },
      {
        "index": 7,
        "score": -0.51,
        "highlight": 0,
        "paragraph": "Certain states have taken matters into their own hands with proposed additional restrictions. Arkansas, for example, is one step away from an in-season ban on all dicamba products."
      }
    ]
  }
]
```
{: codeblock}

By default the response from the API feed is in JSON format.