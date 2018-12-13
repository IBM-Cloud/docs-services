---

copyright:

  years:  2018

lastupdated: "2018-12-13"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About Hydrogen
{: #gettingstarted}

Hydrogen's APIs combine all of the core infrastructure and connectors needed to build leading fintech architecture, with all of the financial engineering needed to build products and tools to set your brand apart.

[Hydrogen Developer Page](https://www.hydrogenplatform.com/developers){:new_window}
[Documentation for Nucleus API](https://www.hydrogenplatform.com/docs/nucleus/v1/){:new_window}
[Documentation for Proton API](https://www.hydrogenplatform.com/docs/proton/v1/){:new_window}
[Documentation for Electron API](https://www.hydrogenplatform.com/docs/electron/v1/){:new_window}

{:shortdesc}

## Getting started

To start using Hydrogen, you must first sign up for an account. [Click here](https://www.hydrogenplatform.com/sign-up){:new_window} to get started!

We provide a free sandbox environment to test our APIs before going into production.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/step1-final_6e57b80a-2c93-49c5-9cdd-1dba4a628150.png)

Login to the developer portal and request access to Atom.

Connect your GitHub and a member of the Hydrogen team reviews access requests daily. Once approved, you'll be able to create credentials.

From the developer portal you can now create credentials upon which you will need to sign a Sandbox Evaluation Agreement.

[Instructions are available here.](https://www.hydrogenplatform.com/docs/nucleus/v1/#OAuth2-Authorization){:new_window}

AUTHENTICATION
API Authentication
After successful registration of your application, you will be provided a `client_id` and `client_secret` which will be used to identify your application when calling any Hydrogen API.

We require all API calls to be made over HTTPS connections.

OAuth2
Hydrogen uses OAuth 2.0 to facilitate authorization on the API, an industry standard framework for authorization. The client credentials flow is used by your application to obtain permission to act on its own behalf. A call will be made to our OAuth server to exchange your `client_id`, `client_secret`, and `grant_type=client_credentials` for an `access_token`, which can then be used to make calls to Hydrogen on behalf of the application.

#### EXAMPLE REQUEST
```
curl -X POST https://api.hydrogenplatform.com/authorization/v1/oauth/token?grant_type=client_credentials \
  -H "Authorization: Basic aHlkcm9nZW5faWQ6aHlkcm9nZW5fc2VjcmV0"
```
#### EXAMPLE RESPONSE
```
{
  "access_token": "ac6b8213-2a77-4ecc-89fd-68c9f2aff256",
  "token_type": "bearer",
  "expires_in": 86400,
  "scope": "create read update delete",
  "apps": "nucleus,proton,electron"
}
```

#### SUBSEQUENT API CALLS
```
curl -X GET https://api.hydrogenplatform.com/nucleus/v1/account \
-H "Authorization: Bearer ac6b8213-2a77-4ecc-89fd-68c9f2aff256"
```

Create a new client, or register a new user, with your firm. The endpoint returns a unique `client_id` that is used to manage the specific client and referenced in other endpoints.

#### EXAMPLE REQUEST

```
curl -X POST -H "Authorization: Bearer e7cf805b-4307-41e9-8b58-90b6359fa900" \
    -H "Content-Type: application/json" \
    -d '{
            "email": "jd@email.com",
            "username": "jd@email.com",
            "client_type": "individual",
            "title": "Mrs.",
            "first_name": "Jane",
            "middle_name": "Mary",
            "last_name": "Doe",
            "phone_number": "987-765-1244",
            "date_of_birth": "1971-12-27",
            "identification_number": "123-44-5566",
            "country_of_residence": "US",
            "is_verified": true,
            "hydro_id": "10lm4nz",
            "is_active": true,
            "metadata": {
                "median_household_income": "10000",
                "net_worth": "100000",
                "occupation": "Business Owner",
                "zillow_home_value": "450000",
                "annual_income": "70000"
            },
            "address": [
                {
                    "address_line1": "3 Downtown Street",
                    "address_line2": "",
                    "city": "New York",
                    "type": "Home",
                    "postalcode": "01191",
                    "country": "US",
                    "state": "NY"
                }
            ]
        }' "https://api.hydrogenplatform.com/nucleus/v1/client"
```

