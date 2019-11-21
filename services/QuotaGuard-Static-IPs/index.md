---

copyright:

  years:  2018

lastupdated: 19 Aug 2018

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# AboutQuotaGuard Static IP
{: #gettingstarted}

QuotaGuard Static allows you to route inbound & outbound traffic through a static IP address. You can provide this IP address to an API partner or external servicefor IP based whitelisting and open your own firewall to access internal resources.

{:shortdesc}

## Getting started

To obtain your QuotaGuard credentials and IP Addresses, go to the "Service credentials" tab for your QuotaGuard Static IPs instance and create/view the Service credentials.

Your credentials will look like this:
```json
{
  "ip_addresses": [
    "54.12.34.56",
    "54.56.34.12"
  ],
  "url": "http://fv5qkl259x6kxp:Izxdf3Kh5fFj_awHfacSLZ9eoA@us-east-static-22.quotaguard.com:9293"
}
```

After obtaining your IP addresses and credentials, you are ready to setup your proxy accordingly.

For additional help, please check out the [Quick Start Guide](https://www.quotaguard.com/support/quick-start?provider=ibm_cloud).