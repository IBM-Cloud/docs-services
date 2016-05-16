{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

## Creating a new test run (multi-page widget)
{: #creating_test_run} 

When you create a test run through the multi-page widget, you need to upload your application and then select the test type.
{:shortdesc}

1. Upload your application

	Click **Choose File** button to locate APK or IPA file from your
  	local harddisk. For further configuration, click *Next* (either
  	on bottom or top of the view).

	![](http://docs.testdroid.com/assets/user-manuals/projects_choose_file.png)
	

2. Select the test type

   Testdroid Cloud provides a feature called App Crawler that
   automatically crawls through the app and tests its functionality by
   exercising UI components (e.g. button clicks, opening menus,
   changing views). App Crawler automatically handles the screenshot
   taking, log writing and generally it keeps the record of
   application's status.

   When user selects 'File' instead of App Crawler the view asks
   user to locate test script files for the app.

   When proper test method has been selected, click *Next* (either
   on bottom or arrow on top).

   ![](http://docs.testdroid.com/assets/user-manuals/projects_choose_file_2.png)

3. Select devices for the test run
 
	The view shows all created device groups. User can also create
	a new device group by clicking the left-top icon with a '+'
	button. Device groups are either for Android or iOS. By
	default, Free device group is selected.
 
	**NOTE!** Device groups can include only Android or iOS devices.

	![](http://docs.testdroid.com/assets/user-manuals/projects_device_groups.png)

4. Advanced options for the test run

   User can specify test run name, tags, scheduling of the test run
   (if tests is desired to be executed simultaneously on all devices,
   one device at a time or on a first available device for test run).

   User can select the language for devices. There is great variety of
   different languages available and all devices will be configured
   with selected language for the test run.

   User can input login credentials for the application. If app
   requires user authentication at the beginning, login and password
   information can be included here.

   User can specify how test cases are used - e.g. from specific
   package or class and then definitely the name in given field.

   User can also specify hooks for finished tests by giving an URL. If
   this option is used, the POST call will be performed when test run
   is finished.

   ![](http://docs.testdroid.com/assets/user-manuals/projects_advanced_options.png)


   Start the test run by clicking Start button. User will now
   redirected to Test Run view.
