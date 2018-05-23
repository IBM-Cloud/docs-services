---

copyright:

  years:  2018

lastupdated: "2018-05-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Best practices for using the PowerAI IBM Cloud service
{: #gettingstarted}

One of the popular use cases for the PowerAI service is training a deep learning neural network model.
{:shortdesc}

This document assumes that the user already has the training dataset in a bucket in IBM Cloud Object Storage (IBM COS).  There are two options to use this training dataset for a training job:

- Download the training dataset from IBM COS into `/scratch` space of the node provisioned by the user to run the training job. The training job can then be run after the training data set has been downloaded into `/scratch`.
- Provide the Cloud Object Storage parameters when the user provisions the node to run the training job. This will automatically make the training data set visible in `/data` after the node is provisioned.  The training job can then be started immediately with the training data visible in `/data`.  Once the training job starts, it will read the training data from IBM COS over the Direct Link via s3fs (which provides a file interface to the training dataset in IBM COS). In this case, there is no need to download the training data from IBM COS to the `/scratch` space before the training job is started.

Which option should be used depends on several considerations.  Using `/scratch` space to hold training data provides the best performance for all training epochs.  Using the Cloud Object Storage option results in slower performance during the first epoch (from 30% to 80% in our testing), but excellent performance for subsequent epochs.

The Cloud Object Storage Object (COS) option can be used in the following use cases:

- If the working set of the training dataset is less than 112GB.  The working set is the amount of data that is actually accessed and used during training sessions.
- If the instance will be deleted frequently.
- If the training jobs are relatively short, which is typical for users experimenting with different neural network models before full training runs.  In this case, the training data would be made visible to `/data` and the training jobs could start immediately after the node is provisioned.  The first epoch would be slow as the training data is actually retrieved from the IBM COS over the Direct Link as the training session commences.  In our testing, the first epoch could be 30% to 80% slower than using `/scratch` for training data.  However, the second and subsequent epochs would be as fast as using `/scratch` because the training data was already cached locally in `/data` during the first epoch.

## Using awscli to Transfer Data From IBM Cloud Object Storage (IBM COS)

As mentioned in the previous section, the fastest way to download the training dataset from IBM COS into the `/scratch` space of a node is to use awscli.  In our testing, the training dataset could be downloaded from IBM COS over Direct Link into the `/scratch` space of a node at up to 750 Mbps (many users downloading or retrieving data from IBM COS at the same time would affect this data transfer rate).

Here are the steps on how to install, configure, and use awscli:

- If the service credentials for the COS have not already been created, create them as documented here: [https://dataplatform.ibm.com/docs/content/analyze-data/ml_dlaas_object_store.html#createcredentials](https://dataplatform.ibm.com/docs/content/analyze-data/ml_dlaas_object_store.html#createcredentials)
- Run `aws configure` and give the access key id and secret access key to the COS as created in the previous step.
- When using the `aws` command, the endpoint URL is the Nimbix proxy endpoint: [https://us-south-objectstorage.jarvice.io](https://us-south-objectstorage.jarvice.io)
- Run `aws --endpoint-url="https://us-south-objectstorage.jarvice.io" s3 cp s3://<bucket name>/ /scratch --recursive`

The additional flags `--exclude` and `--include` can be used to specify particular files from the COS bucket, resulting in reduced overall transfer time.
