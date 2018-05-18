---

copyright:

  years:  2018

lastupdated: "2018-05-17"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with PowerAI in IBM Cloud
{: #gettingstarted}

The PowerAI service on IBM Cloud provides users with access to IBM POWER servers running the PowerAI software. This service is operated in partnership with Nimbix.

{:shortdesc}

## About
{: #about}

PowerAI makes deep learning, machine learning, and AI more accessible and more performant. By combining this software platform for deep learning with IBM® Power Systems™ and NVIDIA® GPUs, enterprises can rapidly deploy instances fully optimized and supported for MLDL with blazing performance. The PowerAI platform includes the most popular machine learning frameworks and their dependencies, and it is built for easy and rapid deployment. Users can also build out multi-node clusters for Distributed Deep Learning (DDL) with Infiniband interconnects. PowerAI is offered in partnership with Nimbix on IBM Power Systems infrastructure.

## Provisioning Options
{: #provisioning}

The PowerAI service presents users with several options when provisioning instances. These options include:

### Pricing Plans
{: #pricingplans}

The pricing plan selected for this service will determine the hardware available for your PowerAI instance. For example, a "Small" plan may only provide a single GPU, while a "Large" plan may provide four GPUs.

### Number of machine nodes
{: #numnodes}

This option, only available when the "Large" pricing plan size is selected, allows a user to create a multi-node cluster. It is specified as the `num_nodes` parameter.

```
{
    "num_nodes": 2
}
```

### Import from Cloud Object Storage
{: #importcos}

This optional feature enables users to provide details for an [IBM Cloud Object Storage](https://www.ibm.com/cloud/object-storage) bucket to be connected to the PowerAI instance when the instance is provisioned. Required parameters are as follows:

Cloud Object Storage bucket name: The name of the single IBM Cloud Object Storage bucket to be connected.
Cloud Object Storage access key: The IBM Cloud Object Storage access key provided in the [IBM Cloud Object Storage HMAC credentials](https://console.bluemix.net/docs/services/cloud-object-storage/iam/service-credentials.html).
Cloud Object Storage secret key: The IBM Cloud Object Storage secret key provided in the [IBM Cloud Object Storage HMAC credentials](https://console.bluemix.net/docs/services/cloud-object-storage/iam/service-credentials.html).

```
{
    "cos_bucket": "myBucket",
    "cos_access_key": "acbdefg",
    "cos_secret_key": "123456"
}
```
{: codeblock}

## Connect to your instance
{: #connect}

After a service instance is provisioned, the service will generate credentials that can be used to connect with the machine via SSH or VNC. These credentials are visible through the service instance dashboard. They can also be obtained via the CLI by creating a service key. Other applications and services can use the service key credentials to connect with the instance.

## PowerAI Usage Documentation
{: #poweraiusage}

Once connected to your instance, documentation for PowerAI is available in the directory

```
/opt/dl/README.md
```

for the overall PowerAI software package, as well as in README files in individual framework subdirectories (/opt/DL/tensorflow/doc/README.md, /opt/DL/tensorflow/doc/README.md, etc)
