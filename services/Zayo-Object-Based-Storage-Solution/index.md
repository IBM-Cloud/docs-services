---

copyright: 2017

years:  2017

lastupdated: "2017-10-30"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Zayo Object Based Storage
{: #gettingstarted}

Zayo Object Based Storage is a web-scale unstructured data storage service, designed for high durability, resiliency and security. You can store and access your data from anywhere and since the service is supported by the global Zayo network, you can move your data in and out of storage with no egress or operational charges. Developers can leverage Zayo Object Based Storage with their applications, with other hyperscale public cloud services, or integrate with other IBM® Bluemix® services including analytics, compute and cognitive services.
{:shortdesc}


Before an application developer can begin to work with Zayo Object Based Storage, services must be stood up within Zayo using the Tranzact portal.

To get up and running quickly with this service, follow these steps:

1. Visit the Zayo Tranzact website located at https://tranzact.zayo.com/#!/get-pricing/cloud/chooseSolution
2. Select the Object-Based Storage tile.
3. If you are an existing Zayo customer, select the location(s) from which you would like to access the service.
4. Create your bucket names and requested sizes.
5. Select your connectivity method, note that removal of egress charges only applies to private circuits.
6. Finalize your quote request with a Zayo service expert.
7. Upon service initialization, you will be provided with access instructions and keys.
8. Complete your Watson integration on the IBM® Bluemix® portal by plugging in your API credentials.

## About Zayo OBS
{: #aboutzayocloudobjectstorage}

Information stored with Zayo OBS is encrypted and dispersed across multiple geographic locations, and accessed through an implementation of the S3 API. This service makes use of the distributed storage technologies provided by IBM’s Cloud Object Storage System (formerly Cleversafe).

Zayo OBS is available in a Cross Region configuration. Cross Region service provides higher durability and availability than using a single region at the cost of slightly higher latency, and is available today in the US. If a given region is unavailable, the object store continues to function without impediment, and any missed changes are applied when the data center comes back online.

Developers use the Zayo OBS implementation of the S3 API to interact with their storage accounts. This documentation provides support to get started with provisioning accounts, to create buckets, to upload objects, and to use a reference of common API interactions. 

This documentation is for anyone interested in learning about how to use Zayo OBS to manage unstructured data IO in their cloud applications, to store large files for machine learning and data analysis, or simply as a tool for backup and other IT services.