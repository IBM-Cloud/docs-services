---

copyright:

  years:  2018

lastupdated: "2018-05-28"

---

# Getting started with Hazard Hub API

[logo]: http://hazardhub.com/wp-content/themes/wp-work/img/header/logo.png
You can use our API to retrieve the risk score cards and other info for any address or point in the USA.

To be able to start using the service you will have to set an authorization header in each request within the API KEY taken from your profile page:
```
Authorization: Token token=[YOUR TOKEN]
```

You will get authorization token automatically after the registration at [api.hazardhub.com](https://api.hazardhub.com/users/sign_up). The token is shown at [api.hazardhub.com/profile](https://api.hazardhub.com/profile) page. You will get a specific amount of requests which can be done per day.

You can use this request to check that the service is working correctly by getting info about your profile:
```
https://api.hazardhub.com/me
```

Example:
```
curl -H "Authorization: Token token=[YOUR TOKEN]" "https://api.hazardhub.com/v1/me" -v
```

Now you can start retrieving the risk score cards and additional data. Each request can work with the plain address or the coordinates (latitude/longitude).

Following request is used to get only the risk score cards and some additional info like driving time from the nearest fire station:
```
https://api.hazardhub.com/risks
```
Example using lat/long:
```
curl -H "Authorization: Token token=[YOUR TOKEN]" "https://api.hazardhub.com/v1/risks?lat=37.757815&lng=-122.5076403" -v

```
Example using address:
```
curl -H "Authorization: Token token=[YOUR TOKEN]" "https://api.hazardhub.com/v1/risks?address=135+Swifts+Beach+Road%2C+Wareham%2C+MA%2C+USA" -v
```

Next request is used to get the information about the property:
```
https://api.hazardhub.com/property
```
Example using lat/long:
```
curl -H "Authorization: Token token=[YOUR TOKEN]" "https://api.hazardhub.com/v1/property?lat=26.653622&lng=-80.0367709" -v
```
Example using address:
```
curl -H "Authorization: Token token=[YOUR TOKEN]" "https://api.hazardhub.com/v1/property?address=1820+South+Ocean+Boulevard&city=Palm+Beach&state=FL&zip=33480" -v
```

If you need both risk report and property info, use this request:
```
https://api.hazardhub.com/risks_and_property
```
Example using lat/long:
```
curl -H "Authorization: Token token=[YOUR TOKEN]" "https://api.hazardhub.com/v1/property?lat=26.653622&lng=-80.0367709" -v
```
Example using address:
```
curl -H "Authorization: Token token=[YOUR TOKEN]" "https://api.hazardhub.com/v1/property?address=1820+South+Ocean+Boulevard&city=Palm+Beach&state=FL&zip=33480" -v
```

Response examples:

```
risks: {
  wildfire: {
    score: "A",
    text: "None"
  },
  wildfire_description: {
    value: "High_Dens_NoVeg"
  },
  wildfire_risk_score: {
    value: "1"
  },
  wildfire_risk: {
    value: "None"
  },
  wildfire_distance_to_high_area: {
    value: 3009.48,
    units: "feet"
  }
  ...
},
property: {
  RecordID: null,
  Result: {
    Code: "YS02,YS03,YC01,GS05",
    Description: "AddressKey Match Found. Basic information returned."
  },
  ...
}
```