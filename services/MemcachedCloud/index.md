---

copyright:

  years: 2016

lastupdated: "2016-05-18"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Memcached Cloud
{: #gettingstarted}

[Memcached Cloud](http://redislabs.com/memcached-cloud) is a fully-managed service for running your Memcached in a reliable and fail-safe manner. Your dataset is constantly replicated, so if a node fails, an auto-switchover mechanism guarantees data is served without interruption. Memcached Cloud provides various data persistence options as well as remote backups for disaster recovery purposes. You can quickly and easily get your apps up and running with Memcached Cloud through its add-on for Codename: BlueMix, just tell us how much memory you need and get started instantly with your first Memcached bucket.

A Memcached bucket is created in seconds and from that moment on, all operations are fully-automated. The service completely frees developers from dealing with nodes, clusters, server lists, scaling and failure recovery, while guaranteeing absolutely no data loss.
{:shortdesc}

## Creating A Memcached Cloud Service

You can use the Codename: [BlueMix web user interface](https://console.ng.bluemix.net/) or the [`cf` command line interface](https://console.ng.bluemix.net/docs/cli/index.html#downloads) to create an instance of the Memcached Cloud service. The following `cf` command creates the service instance:

  ```
    cf create-service memcachedcloud PLAN SERVICE_INSTANCE
  ```
  {: pre}


where `PLAN` is the desired plan (e.g. the free 30mb plan) and `SERVICE_INSTANCE` is the name of the service instance.

## Binding Your Memcached Cloud Service
Use the web user interface or the command line interface to bind a Memcached Cloud service instance to an application. When using `cf`, the following command binds the instance to the application:

  ```
    cf bind-service APP SERVICE_INSTANCE
  ```
  {: pre}
	
where `APP` is the name of the application and `SERVICE_INSTANCE` is the name of the service instance.

Once your Memcached Cloud service is bound to your app, the service credentials will be stored in the `VCAP_SERVICES` environment variable in the following format:
	
  ```
    {
       "memcachedcloud-null": [
          {
             "name": "dev-session-cache",
             "label": "memcachedcloud-null",
             "plan": "30mb",
             "credentials": {
                "username": "...",
                "servers": "pub-memcached-11211.dal-05.1.sl.redislabs.com:11211",
                "password": "..."
             }
          }
       ]
    }
  ```
  {: codeblock}

* [Ruby](#ruby)
* [Rails](#rails)
* [Sinatra](#sinatra)
* [Java](#java)


## <a id="ruby"></a>Using Memcached with Ruby
[Dalli](https://github.com/mperham/dalli) is a high performance pure Ruby client for accessing memcached servers, which uses the binary protocol. 

### <a id="rails"></a>Configuring Memcached from Rails
For usage with Rails 3.x, update the Gemfile:

  ```
	gem 'dalli'
  ```
  {: pre}
	
And then install the gem via Bundler:

  ```
	bundle install
  ```
  {: pre}
  
Parse your credentials as follows:

  ```
	memcachedcloud_service = JSON.parse(ENV['VCAP_SERVICES'])["memcachedcloud-n/a"]
	credentials = memcachedcloud_service.first["credentials"]
  ```
{: codeblock}
	
Lastly, in your `config/environments/production.rb`:

  ```
  config.cache_store = :dalli_store, credentials.servers, { :username => credentials.username, :password => credentials.password }
  ```
  {: codeblock}

### <a id="sinatra"></a>Configuring Memcached on Sinatra
Add this code snippet to your configure block:

  ```
	configure do
    . . .
		require 'dalli'
		memcachedcloud_service = JSON.parse(ENV['VCAP_SERVICES'])["memcachedcloud-n/a"]
		credentials = memcachedcloud_service.first["credentials"]
		$cache = Dalli::Client.new(credentials.servers.split(','), :username => credentials.username, :password => credentials.password)
    . . .
	end
  ```
  {: codeblock}

### Testing (Ruby)
  ```
	$cache.set("foo", "bar")
	# => true
	$cache.get("foo")
	# => "bar"
  ```
  {: codeblock}
    
## <a id="java"></a>Using Memcached with Java
[spymemcached](https://code.google.com/p/spymemcached/) is a simple, asynchronous, single-threaded memcached client written in Java. You can download the latest build from: https://code.google.com/p/spymemcached/downloads/list.

To use the maven repository, start by specifying the repository:
	```
	<repositories>
	    <repository>
	      <id>spy</id>
	      <name>Spy Repository</name>
	      <layout>default</layout>
	      <url>http://files.couchbase.com/maven2/</url>
	      <snapshots>
	        <enabled>false</enabled>
	      </snapshots>
	    </repository>
	</repositories>
	```
	{: codeblock}

And specify the actual artifact as follows: 

  ```
  <dependency>
	  <groupId>spy</groupId>
	  <artifactId>spymemcached</artifactId>
	  <version>2.8.9</version>
	  <scope>provided</scope>
	</dependency>
  ```
  {: codeblock}
  

Configure the connection to your Memcached Cloud service using the `VCAP_SERVICES` environment variable and the following code snippet:

  ```
	try {
		String vcap_services = System.getenv("VCAP_SERVICES");
		if (vcap_services != null && vcap_services.length() > 0) {
			// parsing memcachedcloud credentials
			JsonRootNode root = new JdomParser().parse(vcap_services);
			JsonNode "memcachedcloudNode = root.getNode("memcachedcloud-n/a");
			JsonNode credentials = "memcachedcloudNode.getNode(0).getNode("credentials");
			
			// building the memcached client
			AuthDescriptor ad = new AuthDescriptor(new String[] { "PLAIN" },
			        new PlainCallbackHandler(credentials.getStringValue("username"), credentials.getStringValue("password")));
				
			MemcachedClient mc = new MemcachedClient(
			          new ConnectionFactoryBuilder()
			              .setProtocol(ConnectionFactoryBuilder.Protocol.BINARY)
			              .setAuthDescriptor(ad).build(),
			          AddrUtil.getAddresses(credentials.getStringValue("servers")));
			
		}			
	} catch (InvalidSyntaxException ex) {
		// vcap_services could not be parsed.
	} catch (IOException ex) {
		// the memcached client could not be initialized. 
	}
  ```
  {: codeblock}

	
### Testing (Java)
  ```
	mc.set("foo", 0, "bar");
	Object value = mc.get("foo");
  ```
  {: codeblock}


## Dashboard
Our dashboard presents all performance and usage metrics of your Memcached Cloud service on a single screen, as shown below:

![Dashboard](https://s3.amazonaws.com/paas-docs/memcached-cloud/ibm_bluemix_memcached_cloud_dashboard.png)

To access your Memcached Cloud dashboard, click the service instance in your Code Name: BlueMix console and then the **LAUNCH MEMCACHEDCLOUD DASHBOARD** button.

When using the Memcached Cloud console, you can then find the dashboard using the **MY RESOURCES->Dashboard** menu item.

## Support
Any Memcached Cloud support issues or product feedbacks are welcome via email at support@redislabs.com or from the service's console under the **SUPPORT->Helpdesk** menu item.

# Related Links
{: #rellinks notoc}

## Tutorials and Samples
{: #samples}

* [FAQ](https://redislabs.com/company/faqs?page_source=memcached#memcached){:new_window}
* [HowTo](https://redislabs.com/memcached-howto?page_source=memcached){:new_window}

## Related Links
{: #general}

* [Developers Resources](http://redislabs.com/memcached-cloud){:new_window}
* [Memcached Wiki](https://code.google.com/p/memcached/wiki/NewStart){:new_window}
