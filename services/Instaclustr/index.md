
---

copyright:

  years: 2016

lastupdated: "2016-07-15"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Instaclustr Cassandra
{: #gettingstarted}

Instaclustr provides a cloud hosted, fully managed Apache Cassandra NoSQL database. Cassandra is a distributed database that can store huge amounts of data, whilst providing linear scalability, continuous availability and low latency data access. We provide a fully managed service that includes 24/7 support, monitoring and alerting, system patches and updates, daily backups, and automated system repairs. We are a team of Cassandra experts with hundreds of thousands of node-hours experience running Cassandra, and our performance-optimized Cassandra solutions power mission-critical always-on applications.
{:shortdesc}


## Adding the Instaclustr service
### Selecting a plan
We recommend you select a plan based on the anticipated size of your database, unless your application requires high throughput (>2,000 operations/second). To determine the correct plan, use the estimated size of your database, plus 50% to allow for Cassandra internal operations such as compactions.


Note: Storage Capacity and Memory are derived from the values quoted by the infrastructure provider and are an approximation only. Storage capacity and memory available to Cassandra may be less. A Keyspace replication factor of 2 or higher will reduce available storage capacity.


### Bind the service in Bluemix
This article does not explain the commands used to manage your apps and services on Bluemix. Please see the detailed Bluemix docs for how to get started with Bluemix.


To add Instaclustr to your account from the Bluemix console, select Instaclustr from the Bluemix services catalog. Next, select your plan (see note above) and app if you wish to bind immediately.


Instaclustr service can also be added using the CLI:

  	```
	create-service instaclustr
	```
	{: pre}
	
Note: Overall cluster provisioning process on SoftLayer plans may take up to 2 days to allow for bare metal servers to be provisioned.


## Console
To access information about the current status of your cluster, as well as connection information and detailed real-time and historical monitoring statistics, select the Instaclustr service from your Bluemix Dashboard.

### Monitoring
The Instaclustr console gives you access to detailed real-time information about the status and performance of your cluster. To access this feature select the ‘Monitoring’ tab from the Cluster Details page.


## Connecting to your cluster
Once your cluster has been provisioned (check the console for RUNNING status), the credentials will be in your VCAP_SERVICES environment variable. Use the cf env command to view your connection info: 

  	```
	{
		"metadata": [
		  {
		    "username": "iccassandra",
		    "password": "yourclusterpassword",
		    "endpoints": ["10.240.10.20", "10.240.11.244", "10.240.10.217"],
		    "port": "9042",
		    "clusterCertificateDownload": "<url|disabled>"
		  }
		]
	}
	```
	{: screen}

To connect to your Cassandra cluster, you may open a connection to any contact point using the username and password provided. Typically you provide a list of all nodes in the cluster and your client driver will manage connections and retries.


The following sections will show you how to connect to your cluster using Python, but there is also supported Cassandra drivers for Java, Ruby, node.js, and Go, and many more.

### A note on SSL
If you are on a paid plan your cluster is configured to use client to server encryption (SSL) by default. You will need to provide the cluster certificate to the connection command.


You can obtain your cluster certificates from the Instaclustr console.


It is highly recommended that you create a non-superuser account for your app rather than using the iccassandra account for general access. To do this, connect to your cluster and use the following CQL command. Alternatively, you can contact our support team to have this user created for you.

  	```
	CREATE USER IF NOT EXISTS newuser WITH PASSWORD 'password';
	```
	{: pre}

## Sample App
The easiest way to get started is to clone our "quick start" app published on our github repository.

  	```
	git clone ......
	```
	{: pre}

### Getting started using Python
This section shows you how to start using Cassandra from an application written in Python. You can use this as a starting point for apps written in other languages, as the steps are the same.

### Dependencies
Add the Cassandra driver to your requirements.txt file.

  	```
	cassandra-driver==2.5.1
	```
	{: pre}

### Connecting to the cluster
Connect to your cluser using the credentials given in your VCAP_SERVICES environment variable.

	```
	cluster = Cluster(
    	contact_points=['XX.XX.XX.XX', 'XX.XX.XX.XX', 'XX.XX.XX.XX'],
    	auth_provider=PlainTextAuthProvider(
        	username='iccassandra',
        	password'yourclusterpassword')
  	)
  	session = cluster.connect()
  	session.default_timeout = 120
	print 'Connected to cluster %s' % cluster.metadata.cluster_name
  	for host in cluster.metadata.all_hosts():
    	print 'Datacenter: %s; Host: %s; Rack: %s' % (host.datacenter, host.address, host.rack)
	```
	{: codeblock}

### Creating a keyspace and table
The first thing you need to do after connecting to you cluster is create a keyspace and column families (tables) to store your data. This example also shows how to optionally specify some table properties such as compaction and compression options.


Instaclustr recommends using only NetworkTopologyStrategy as this ensures proper distribution of your data across racks.


replication_factor determines how many copies of each row is stored to ensure reliability and fault tolerance. You should set the replication factor equal to the number of nodes in your cluster (3).

  	```
	session.execute("CREATE KEYSPACE IF NOT EXISTS sensor_data WITH replication = {'class': 'NetworkTopologyStrategy', 'DAL01':3};")
	session.execute("CREATE TABLE IF NOT EXISTS sensor_data.raw (
            device text,
            sensor text,
            time timestamp,
            metric double,
            PRIMARY KEY ((device, sensor), time)
        ) WITH CLUSTERING ORDER BY (time DESC)
            AND compaction = {'max_sstable_age_days': '0.05', 'base_time_seconds': '300', 'class': 'org.apache.cassandra.db.compaction.DateTieredCompactionStrategy'}
            AND compression = {'sstable_compression': 'org.apache.cassandra.io.compress.LZ4Compressor'}
            AND gc_grace_seconds = 0;")
	```
	{: codeblock}

Cassandra uses the first part of the primary key as the partition key. This determines the node on which the row will be stored. As all rows with the same partition key are stored on the same node, you should choose a data type with high cardinality to ensure an even distribution of data across the cluster.

Using the right partition and primary keys is crucial to a well functioning Cassandra implementation, so we recommend you learn about these concepts if not familiar with them.

### Reading and Writing data
To insert rows, use the CQL INSERT statement.

  	```
	ssession.execute("INSERT INTO sensor_data.raw (device, sensor, time, metric) VALUES ('328faaaa-f9a8-42b9-9fcd-4fb6ad70e843','temperature',datetime.datetime.strptime('2016-02-01 11:59:36', \"%Y-%m-%d %H:%M:%S\"),float(17.47735)")
	```
	{: codeblock}
	
To retrieve data use CQL SELECT. 

	```
	results = session.execute("SELECT device, sensor, time, metric FROM sensor_data.raw")
        for row in results: print row.device, row.sensor, row.time, row.metric
	```
	{: codeblock}

To learn more about Instaclustr and Cassandra, check out the documentation and tutorials on our support site.

## Related Links
{: #general}

* [Instaclustr Home](https://www.instaclustr.com/){:new_window}
* [Instaclustr Git Repository](https://github.com/instaclustr){:new_window}
* [lnstaclustr Support Site](https://support.instaclustr.com/hc/en-us){:new_window}
