# Getting started with Xpertrule for Bluemix

### Publish knowledge in Web Author
1. Login to Web Author.
```
http://ibmxrkb.xpertrule.com/
```

2. Open Bluemix App and publish the knowledge, Menu -> Publish.. -> Publish the current Knowledge Base.

3. Copy the url for later use in Node-Red.

### Use published knowledge in a Bluemix Node-Red app
1. Login to Bluemix, create a Node-Red starter application and download the starter code by taking the following steps.

	1.1. Create a Node-Red starter applications from the Bluemix catalogue.

	1.2. Provide the app name and host.

2. Go to the Getting Started tab and download the code by clicking Download Starter Code. 

3. Open a new Command Promp window and change the directory to where you placed the node-red starter code.
```
cd directory_name
```

4. Install the xrcall node red node, which will be used for running the knowledge published earlier. This step requires you to have [npm](https://www.npmjs.com/) installed.
```
npm install node-red-contrib-xrcall
```

5. With the new xrcall code, push the Starter Code back to bluemix.

	5.1. Download and install CF Command Line Interface.
	```
	https://github.com/cloudfoundry/cli/releases
	```

	5.2. Connect to IBM Bluemix.
	```
	cf api https://api.ng.bluemix.net
	```

	5.3. Log in to Bluemix.
	```
	cf login
	```

	5.4 Upload the app to bluemix.
	```
	cf push app_name
	```

6. Access your new node-red and import the flow below by clicking Menu -> Import -> Clipboard using copy/paste. 
```
[{"id":"db2e43f6.4c3d1","type":"xrcall","z":"66f711b2.8ba8b","name":"XpertRule Knowledge","host":"ibmxrkb.xpertrule.com","port":"8125","path":"Super_Admin_All_Users_Bluemix_App","x":440,"y":90,"wires":[["39b3c085.676da"]]},{"id":"90f107ec.c83858","type":"inject","z":"66f711b2.8ba8b","name":"Manual Trigger","topic":"","payload":"","payloadType":"date","repeat":"","crontab":"","once":false,"x":118,"y":90,"wires":[["b86b43cf.cce65"]]},{"id":"39b3c085.676da","type":"debug","z":"66f711b2.8ba8b","name":"","active":true,"console":"false","complete":"true","x":615,"y":91,"wires":[]},{"id":"b86b43cf.cce65","type":"function","z":"66f711b2.8ba8b","name":"Inputs","func":"msg.Cost = 0;\nmsg.Department = \"Sales\";\nmsg.Grade = \"Director\";\nmsg.In_London = false;\n\nreturn msg;","outputs":1,"noerr":0,"x":268,"y":90,"wires":[["db2e43f6.4c3d1"]]}]
```

7. Double click the xrcall node and change the information to the location of the knowledge you deployed earlier.
```
Host: ibxrkb.xpertrule.com
Port: 8125
Path: User_Bluemix_App
```