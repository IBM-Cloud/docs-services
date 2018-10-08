---

copyright:
  years: 2018
lastupdated: "2018-10-15"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}


# Getting started with IBM Log Analysis with LogDNA
{: #getting-started}

Use IBM Log Analysis with LogDNA to add log management capabilities to your {{site.data.keyword.Bluemix}} architecture. IBM Log Analysis with LogDNA is operated by LogDNA in partnership with {{site.data.keyword.IBM_notm}}.
{:shortdesc}

## Before you begin
{: #prereqs}

You must have a user ID that is a member or an owner of an {{site.data.keyword.Bluemix_notm}} account. To get an {{site.data.keyword.Bluemix_notm}} user ID, go to: [Registration ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/registration/){:new_window}.

Work in the US-South region.

## Step1: Provision an instance
{: #step1}

To provision an instance of IBM Log Analysis with LogDNA through the {{site.data.keyword.Bluemix_notm}} UI, complete the following steps:

1. Log in to your {{site.data.keyword.Bluemix_notm}} account.

    The {{site.data.keyword.Bluemix_notm}} dashboard can be found at: [http://bluemix.net ![External link icon](../../../icons/launch-glyph.svg "External link icon")](http://bluemix.net){:new_window}.

	After you log in with your user ID and password, the {{site.data.keyword.Bluemix_notm}} UI opens.

2. Click **Catalog**. The list of the services that are available in {{site.data.keyword.Bluemix_notm}} opens.

3. To filter the list of services that is displayed, select the **Developer Tools** category.

4. Click the **IBM Log Analysis with LogDNA** tile.

5. Select a service plan. By default, the **Free** plan is set.

6. Select a resource group. By default, the **default** one is set.

7. To provision the LoIBM Log Analysis with LogDNAgDNA service in the {{site.data.keyword.Bluemix_notm}} resource group where you are logged in, click **Create**.

After you provision an instance, you get an ingestion key, also referred to as the service instance APIkey.


**Note:** To provision an instance of LogDNA through the CLI, see [Provisioning LogDNA through the {{site.data.keyword.Bluemix_notm}} CLI]().


## Step2: Configure your Kubernetes cluster to send logs to your instance
{: #step2}

To configure your Kubernetes cluster to send logs to your IBM Log Analysis with LogDNA instance, you must install a `logdna-agent` pod on each node of your cluster. The LogDNA agent reads log files from the pod where it is installed, and forwards the log data to your LogDNA instance.

To configure your Kubernetes cluster to forward logs to your LogDNA instance, complete the following steps:

1. Add a secret to your Kubernetes cluster. This secret contains the LogDNA ingestion key. The LogDNA ingestion key is used to authenticate the logging agent with the IBM Log Analysis with LogDNA service. It is used to open a secure web socket to the ingestion server on the logging back-end system.

    Run the following command:

    ```
    kubectl create secret generic logdna-agent-key --from-literal=logdna-agent-key=YOUR_LOGDNA_INGESTION_KEY
    ```
    {: pre}

2. Configure the LogDNA agent on every worker (node) of your Kubernetes cluster. This agent is responsible for collecting and forwarding your logs.

    Run the following command:

    ```
    kubectl create -f https://raw.githubusercontent.com/logdna/logdna-agent/master/logdna-agent-ds.yaml
    ```
    {: pre}

    The agent collects automatically logs with extension *.log and extensionless files that are located under /var/log. By default, logs are collected from all namespaces, including the kube-system.


## Step 3: Launch the LogDNA Web UI
{: #step3}

To launch the IBM Log Analysis with LogDNA Web UI, see [Launching the IBM Log Analysis with LogDNA Web UI]().

Then, learn how to [filter logs](https://docs.logdna.com/docs/filters), [search logs](https://docs.logdna.com/docs/search), and [define views](https://docs.logdna.com/docs/views).


## Next steps
{: #next_steps}

[Configure alerts.](https://docs.logdna.com/docs/alerts)