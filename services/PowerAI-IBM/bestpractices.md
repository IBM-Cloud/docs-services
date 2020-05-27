---

copyright:

 years: 2019

lastupdated: "2019-02-06"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Best practices for using the PowerAI IBM Cloud service
{: #best-practices}

This guide provides best practices for one of the popular use cases for the PowerAI service - training a deep learning neural network model.
{:shortdesc}

## Using a training dataset
{: #using-training-dataset}

The best practices outlined here rely on a training dataset existing in an IBM Cloud Object Storage (IBM COS) bucket. To learn how to create and upload data to a bucket, see [https://cloud.ibm.com/docs/services/cloud-object-storage/getting-started.html](https://cloud.ibm.com/docs/services/cloud-object-storage/getting-started.html).

There are two preferred options for accessing this training dataset for a training job:

- Download the training dataset from IBM COS into the `/scratch` space of the node, then run the training job.
- Provide the Cloud Object Storage parameters when the user provisions the node. This will automatically make the training dataset visible in the `/data` space after the node is provisioned. The training job can then be started immediately. Once it starts, it will read the training data from IBM COS over the Direct Link via s3fs (which provides a file interface to the training dataset in IBM COS).

Which option should be used depends on several considerations. Using the `/scratch` space to hold training data provides the best performance for all training epochs. Using the Cloud Object Storage option results in slower performance during the first epoch (from 30% to 80%), but excellent performance for subsequent epochs.

The `/scratch` (SSD-backed) storage in a node should be used to hold training data if one of the following is true:

- If the working set of the training dataset is larger than 112GB.  The working set is the amount of data that is actually accessed and used by the training job.
- If the time to download the training dataset is small compared to the length of the training job, which could take days or even weeks.
- If the instance does not go away any time soon.  In this case, it would be more efficient to download the training dataset from IBM COS to `/scratch` once, and then all training jobs can be executed very quickly using that data.

The Cloud Object Storage Object (COS) option works best for the following use cases:

- If the working set of the training dataset is less than 112GB. The working set is the amount of data that is actually accessed and used during training sessions.
- If the instance will be deleted frequently.
- If the training jobs are relatively short, which is typical for users experimenting with different neural network models before full training runs. In this case, the training data can be made visible to `/data` and the training jobs can start immediately after the node is provisioned. The first epoch would be slower than usual as the training data is retrieved from IBM COS over the Direct Link.

## Using awscli to Transfer Data From IBM Cloud Object Storage (IBM COS)
{: #using-awscli}

The fastest way to download the training dataset from IBM COS into the `/scratch` space of a node is to use awscli. Based on performance tests, the training dataset can be downloaded from IBM COS over Direct Link into the `/scratch` space of a node at up to 750 Mbps. This transfer rate may vary based on current service utilization.

Here are the steps on how to install, configure, and use awscli:

- If the service credentials for COS do not exist yet, create them as documented here: [https://dataplatform.ibm.com/docs/content/analyze-data/ml_dlaas_object_store.html#createcredentials](https://dataplatform.ibm.com/docs/content/analyze-data/ml_dlaas_object_store.html#createcredentials)
- Run `aws configure` and use the access key id and secret access key to the COS provided in the previous step.
- Run `aws --endpoint-url="https://us-south-objectstorage.jarvice.io" s3 cp s3://<bucket name>/ /scratch --recursive`.

The additional flags `--exclude` and `--include` can be used to specify particular files from the COS bucket, resulting in reduced overall transfer time.
