---

copyright:

  years:  2017

lastupdated: "2017-04-06"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Orange IoT Connect Express on Bluemix
{: #gettingstarted}

Orange IoT Connect Express provides a simpler and more efficient way to manage all your SIM cards, personalize their services, carry out remote analysis and reduce your operational costs. Our M2M API enables you to build services that seamlessly integrate all the information provided by your M2M SIM cards, allowing you to manage your SIM fleet in real-time.
{:shortdesc}

To get started using Orange IoT Connect Express check out the full [Services overview](./OrangeIoTCE_Services_overview_v1.2.pdf).

After connecting the service to your application, you will have a VCAP_SERVICES environment variable that will have the three bits of information from the tile: login, password and (hardcoded) url. The credentials are valid for all APIs, endpoints for each API will be added to the url.

	```
	"VCAP_SERVICES": {
	 {"user-provided": [
	    {"credentials": {
		"login": "xxx",
		"password": "xxx",
		"url": "https://iosw-ba.orange.com/MLM_EXT_IMC/"
	      },
	      "syslog_drain_url": "",
	      "label": "user-provided",
	      "name": "Orange_IoT_Connect_Express",
	      "tags": []
	    }
	  ]
	 }
	}

	```
	{: screen}

And you will find on the Ressource tab all you need about the Orange IoT Connect Express APIs : the endpoints, the quotas, the documentation and the WSDL package.


<!-- Rellinks moved to toc file for new nav 
## API Reference
{: #api}

* [API WSDL Package](./WSDL.zip){:new_window}

* [API End Points](./EndPoints.txt){:new_window}
* [API Quotas](./Quotas.txt){:new_window}

* [API Connectivity Directory](./DVS107-WSDL-CD.pdf){:new_window}
* [API Customer Catalogue](./DVS107-WSDL-CC.pdf){:new_window}
* [API Option Management](./DVS107-WSDL-OM.pdf){:new_window}
* [API Ordering](./DVS107-WSDL-ORD.pdf){:new_window}
* [API SIM Lifecycle Management](./DVS107-WSDL-SLM.pdf){:new_window}
* [API Traffic Tracking](./DVS107-WSDL-TT.pdf){:new_window}
* [API Session History](./DVS107-WSDL-SH.pdf){:new_window}
* [API Alarm](./DVS107-WSDL-SCA-V2.pdf){:new_window}
* [API Device Info](./DVS107-WSDL-DIS.pdf){:new_window}



## Related Links
{: #general}
-->
