---

copyright:

  years:  2018

lastupdated: "2018-04-06"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Alloy
{: #gettingstarted}

Alloy is a platform to know your customers. We make KYC/AML/CDD effective and simple by providing one API to many data sources, a customizable rules engine, modeling capabilities, as well as advanced analytics and auditing.
{:shortdesc}

To integrate your app with the service, complete these steps:

# Using the Alloy API

## Authentication

Basic HTTP authentication and OAuth 2.0 are both supported depending on the security requirements and technical limitations of the organization. Each of your applications is issued a `application_token` and `application_secret` (viewable in your dashboard) that are used in either method.

### Basic HTTP Authentication

 To authorize per-request with HTTP basic auth, use this code:

```
curl -X POST https://sandbox.alloy.co/v1/evaluations \
     -H "Content-Type: application/json" \
     -u dpDD6z4olOSI7N4fMCsAlKjFa7reBYhu:oJm3niQX1Pdy4z675kefEIKBgFn9tQ45 \
     -d $'{
       "name_first": "John",
       ...<other parameters>...
     }'
```
{: codeblock}

If choosing to use HTTP basic auth, credentials must be passed for each request with the username being the `application_token` and the password as the `application_secret`. To implement HTTP basic auth yourself, the steps are as follows:

1. Concatenate the application token and application secret together, separated by a colon
2. Base64 encode the resulting string
3. Pass the result in the authorization header, prefixed with the word "Basic" like `Basic base64_encode(application_token:application_secret)`


## Customer Onboarding

### Get Parameters Needed for Evaluation

Our API is very dynamic, and thus the input parameters vary greatly depending on which services are run and how the application is configured. Hitting the `GET /parameters` endpoint will show exactly what your initial request to the Alloy API should look like. All attributes will either be "required", "optional", or required in certain cases. For instance, in the case to the right, you either have to pass `document_ssn` OR `document_license` and `document_license_state`.

```
curl -X GET https://sandbox.alloy.co/v1/parameters \
    -u dpDD6z4olOSI7N4fMCsAlKjFa7reBYhu:***secret***
```
{: codeblock}

### Onboard a person

This endpoint is for creating a user and running all KYC checks that you have selected for your onboarding flow. If we are able to resolve the person and there is no need for further information, the response will return all the attributes we were able to match and deduce from the services that were run. If more information is needed, the response will indicate what is needed and what the format for that information should be.

```bash
curl -X POST https://sandbox.alloy.co/v1/evaluations \
  -H "Content-Type: application/json" \
  -u dpDD6z4olOSI7N4fMCsAlKjFa7reBYhu:***secret*** \
  -d $'{
    "phone_number": "18042562188",
    "name_first": "John",
    "name_last": "Smith",
    "email_address": "john.smith@example.com",
    "birth_date": "1785-01-23",
    ...<other parameters>...
  }'
```
{: codeblock}

## Other Information

This is all you need to know for basic API usage! For other edge cases scenarios, you can visit our [docs](https://docs.alloy.co).