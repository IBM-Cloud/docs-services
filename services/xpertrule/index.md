# Getting started with Xpertrule for Bluemix

### Publish knowledge in Web Author
1. Login to XpertRule Web Author using your email and password
```
http://ibmxrkb.xpertrule.com/
```

2. The launch screen will contain a default knowledge base called ‘Bluemix Sample’. For details on how to author this knowledge base please visit:
```
http://alphaxrkb.xpertrule.com/editor/help/transactional_getting_started_1.html
```

For now we will concentrate on publishing the sample knowledge base for use in a Node-RED app.

3. Open the ‘Bluemix Sample’ by double clicking. 
	- Locate the Hamburger Menu to the left of the screen
	- -> Publish
	- In the new window select -> Publish the current Knowledge Base  

A url will now appear, please copy for later use in Node-RED

## Publishing a Knowledge Base into a Bluemix Node-RED app
1. Login into the NEW Bluemix site using your relevant email and password. (if you login into the current Bluemix site please select ‘Try the new Bluemix’ from the top right corner)

	- Select Catalogue from the top menu
	- Under the category  ‘Boiler Plates’ select ‘Node-RED Starter’
	- In the new screen provide an App name (avoid using spaces) and Host and select  your relevant plan 
	- -> Create

2.  In the new screen scroll down to the ‘Download Starter Code’ button and press. 

	- Once downloaded please unzip and copy the folder to a location of your choice

3. Open a new Command Promp window

	- Change the directory to where you placed the node-red starter code. 
	```
	cd directory_name
	```

4. Next we need to Install the xrcall node red node (which will be used for running the knowledge base we published earlier)

	- This step requires you to have npm installed. If you don’t already have it installed we recommend downloading Node.js where it comes packaged (nodejs.org)

	- Return to your Command Promp window and run the following command
	```
	npm install node-red-contrib-xrcall
	```

If you have installed the xrcall node correctly you will find it in the ‘node modules folder’

5. We now need to push the ‘Starter Code’ along with the new xrcall node back to Bluemix.

	- Start by downloading and installing CF Command Line Interface.
	```	
	https://github.com/cloudfoundry/cli/releases
	```

	- Return to your Command Promp window and connect to IBM Bluemix with the follwing 
	```
	cf api https://api.ng.bluemix.net
	```

	- Again from your Command Promp window we now need to log into Bluemix with the follwoing
	```
	cf login
	```

	Again you will need to enter your relevant Bluemix email and password

	- Now we Upload the app to Bluemix using the following prompt:
	```
	cf push (insert the name of your newly created Bluemix app)
	```

	This may take a few minutes

6. Access your updated node-RED by returning to the Bluemix site -> Cloud Foundry Application

	- Locate the relevant App and click the associated URL

	- A new window will open called Node-RED in Bluemix. Locate and press ‘Go to your Node-RED flow editor

	- Within the newly opended editor locate the hamburger menu. Menu -> Import -> Clipboard

	- Paste the following flow into the newly opened window:
	```
	[{"id":"db2e43f6.4c3d1","type":"xrcall","z":"66f711b2.8ba8b","name":"XpertRule Knowledge","host":"ibmxrkb.xpertrule.com","port":"8125","path":"Super_Admin_All_Users_Bluemix_App","x":440,"y":90,"wires":[["39b3c085.676da"]]},{"id":"90f107ec.c83858","type":"inject","z":"66f711b2.8ba8b","name":"Manual Trigger","topic":"","payload":"","payloadType":"date","repeat":"","crontab":"","once":false,"x":118,"y":90,"wires":[["b86b43cf.cce65"]]},{"id":"39b3c085.676da","type":"debug","z":"66f711b2.8ba8b","name":"","active":true,"console":"false","complete":"true","x":615,"y":91,"wires":[]},{"id":"b86b43cf.cce65","type":"function","z":"66f711b2.8ba8b","name":"Inputs","func":"msg.Cost = 0;\nmsg.Department = \"Sales\";\nmsg.Grade = \"Director\";\nmsg.In_London = false;\n\nreturn msg;","outputs":1,"noerr":0,"x":268,"y":90,"wires":[["db2e43f6.4c3d1"]]}]
	```

	- Press Import and place your newly created flow onto the open editor.

7. Double click the xrcall node

	- Access the published URL you created earlier in XpertRule Webauthor. Use it to complete the relevant fields as per the example below.
	```
	Host: ibxrkb.xpertrule.com
	Port: 8125
	Path: User_Bluemix_App
	```

	- Press Done

8. Test the knowledge by pressing Deploy and do a manual trigger. The outcome will be displayed in the debug window.
