---

copyright:

  years:  2016

lastupdated: "2016-11-29"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with XpertRule Decision & Rules Automation
{: #gettingstarted} 

XpertRule Decision & Rules Automation for Bluemix is a tool for capturing and automating expert knowledge and decision making. Ideal for complex diagnostics, algorithms / calculations, root cause analysis, troubleshooting and decisions. Used by non-technical domain experts to combine data with knowledge and experience. Ingest any data source, apply decision automation and deliver rapid business outcomes. Used for Industrial IoT condition monitoring, Healthcare diagnostics, Smart Home Insurance IoT and Performance Impovement in Financial Services. 
{:shortdesc}

## Publishing knowledge in Decision Author
1. Log in to XpertRule Decision Author by using your email and password: [http://ibmxrkb.xpertrule.com/](http://ibmxrkb.xpertrule.com)
{:new_window}

	The launch page contains a default knowledge base called ‘Transactional’. For details about how to author this knowledge base, see the following web site:  [http://ibmxrkb.xpertrule.com/editor/help/transactional_getting_started_1.html](http://ibmxrkb.xpertrule.com/editor/help/transactional_getting_started_1.html)
{:new_window}

	For now we will concentrate on publishing the sample knowledge base for use in to node.js

2. Once you have located the Transactional knowledge base, duplicate it by:
	- Selecting the Hamburger menu
	- Select Duplicate
	- Enter a name and OK

3. Open the newly created Knowledge Base by clicking on it
	- Locate the Hamburger menu to the left of the screen
	- ->  Deploy Knowledge Base  -> XpertRule Node.js Server
	- Enter XpertRule Nodejs server details:

	```
	Server IP address: 	ibmxrkb.xpertrule.com
	Port No: 		8125
	Server Password: 	xrkb
	```

	The pop up will display a url, copy it to use later. Press done. Exit Decision Author

## Publishing a knowledge base into a Bluemix node js app

1. Now as an example we will show how to call the deployed ‘Transactional’ knowledgebase from a bluemix application. For the purposes of this demo we have created a sample app which contains the necessary code to call the knowledge base from a bluemix application. 

	- Access this github repository 
	```
	https://github.com/XpertRule/Bluemix-Nodejs-Getting-Started
	```
	- -> Clone or download
	- -> Download Zip
	- Unzip the downloaded file and store in a place you’ll remember

	At this point you open the main.js file located in the downloaded folder to familiarise yourself with the code that will call the knowledge base and enter/update the knowledge object with the parameters of the knowledge base you published a little earlier.

	So for example, from the URL published earlier, just copy the path name and paste it into knowledge.request_path in the main.js file 
	http://ibmxrkb.xpertrule.com:8125/pathname 

2. Next, open a new command prompt

	- Change the directory to where you placed your downloaded zip file.
	```
	cd directory
	```

3. Next, publish the getting started code as an app on Bluemix

	- Start by downloading and installing the cf Command Line Interface.
	```
	https://github.com/cloudfoundry/cli/releases
	```
	- Return to your command prompt and connect to IBM Bluemix by entering the following command:
	```
	cf api https://api.ng.bluemix.net
	```
	- From your command prompt, log in to Bluemix by entering the following command:
	```
	cf login
	```
  	- Enter your relevant Bluemix email address and password when prompted
	- Once your credentials have been accepted, upload the app to Bluemix by using the following command:
	```
	cf push (insert a name for the app)
	```
	
After a few minutes you should be presented with a URL for the newly created bluemix app.  
Calling the app URL does a http request to the knowledge base passing inputs and the desired outputs and returning the inference outcome.
The Transactional knowledge base used in this demo is just a small example of the complex decision making that you can author with XpertRule Decision Author.
