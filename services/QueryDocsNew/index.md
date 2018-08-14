---

copyright:

  years: 2018

lastupdated: "8/2/2018"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About QueryDocs
{: #gettingstarted}

QueryDocs can be used to create 100% customizable reports and dashboards.

{:shortdesc}

## Getting started

To get started please follow these steps:

Make sure you have an account for QueryDocs. You can sign up [here](https://www.tinyqueries.com/signup).

After you [login](https://www.tinyqueries.com/login) you can fill in your database credentials in the settings page: [https://compiler1.tinyqueries.com/ide/#/config](https://compiler1.tinyqueries.com/ide/#/config) 
If needed an SSH-tunnel to your database-server can be created for an encrypted connection.

On your laptop create a folder in which you create the following two files:

* _model.yml
  ```yaml
  # Can be left empty for this example
  ```


* hello-world.yml
  ```yaml
  # This document displays Hello World
  doc hello-world:
    type: sheet
    query:
      select: "'Hello World' as 'message'"

Make sure you have your API-key available; you can see it in the dashboard-screen after you login. You can now use curl to create your first QueryDoc:

```
curl -F api_key=12345 \
  -F project=my-project \
  -F output=querydocs \
  -F files[]=@_model.yml \
  -F files[]=@hello-world.yml \
  https://compiler1.tinyqueries.com/api/compile/
```

The reponse of this call should contain a link to the QueryDoc:

```xml
<?xml version="1.0"?>
<querydocs>
  <root>
    <name>My Project</name>
    <url>https://querydocs.com/{token}</url>
  </root>
</querydocs>
```

The URL can be opened in your browser to view the document.