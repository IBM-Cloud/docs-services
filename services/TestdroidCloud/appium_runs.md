{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Running Appium Tests
{: #using} 

*Last updated: 13 September 2016*
 
Testdroid Cloud supports running Appium tests either remotely (client run) or in the cloud (server side run).
{:shortdesc}


There are different approaches to use Appium for app testing. First, the client-side execution means the application is uploaded to Testdroid Cloud and tests are executed remotely againts Testdroid Cloud. Despite all tests are executed on Testdroid infrastructure and devices. The control over the test execution is outside of Testdroid Cloud. After test execution screenshots are stored on local machine running the tests and results and logs need to be fetched from Testdroid Cloud.

In server-side execution tests and the app under test are upload to Testdroid Cloud. On Testdroid Cloud the devices group to run the tests on needs to be selected and any additional app specific parameters for the test run need to be defined. The results become available in Testdroid Cloud dashboard. The server side execution provides an easier way to start, manage and review tests and gives a way to keep all test assets in one place.

Furthermore, server-side execution provides the way to simultanously run tests on different devices in parallel. With client-side execution one test session per device can be used. There are naturally ways to use instigator scripts to start lots of test runs but the server-side execution makes the parallel execution much easier. In addition, tests Desired Capabilities don't need to be updated, as test scripts are running locally in cloud rather than through an active connection from the user.

 
## Client Side Appium

To run Appium tests remotely to Testdroid Cloud some steps need to be followed. The simplest way is to follow the sample scripts from [Bitbar's Github](https://github.com/bitbar/testdroid-samples/). In summary:

* get user's API key from Testdroid Cloud's UI. It can be found under user's avatar and 'My account'. This API key allows communication with Cloud without needing to store username and password pair to test scripts.

* upload the app under test to Testdroid Cloud eg. using the curl command or create a helper script. In below example `xYY5...PeOA6` is the API key from the user's account page.

  ```bash
  $ curl -H "Accept: application/json" -u xYY5...PeOA6: -F myAppFile=@"/absolute/file/path/example.apk" http://appium.testdroid.com/upload

  {"status":0,"sessionId":"bb8d4336-e6ea-4ba7-9b4c-a6824f1c60aa","value":{"message":"uploads successful","uploadCount":1,"rejectCount":0,"expiresIn":1800,"uploads":{"myAppFile":"bb8e4336-e6ea-4ba7-9b4c-a6824f1c60aa/Testdroid.apk"},"rejects":{}}}
  ```
* update the Appium capabilities with user's API key, the app name (output of above upload), location for screenshots on localhost and names for your project and test run. If some spefic device is required then it needs to be defined into the desired capabilities.

* launch test run on selected device. If no device was selected Cloud will pick some appropriate available device.

After tests are run screenshots can be found in the requested location and logs inside of Testdroid Cloud. For a more detailed example please refer to [user documentation](http://docs.testdroid.com/appium/examples/).
 
## Server Side Appium
 
Server side Appium tests are executed as when running tests locally, with the exception that test is started using a `run-tests.sh` shell script. Java and Python examples can be found in [user documentation](http://docs.testdroid.com/appium/examples/).
