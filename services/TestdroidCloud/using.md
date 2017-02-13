{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Using Bitbar Testing Cloud
{: #using} 

*Last updated: 16 May 2016*
 
The main menu at Bitbar Testing Cloud provides its users a quick way to navigate through the cloud service and access the main features of it. 
{:shortdesc}

Currently, the following items are available on menu:
 
![](http://bitbar.com/wp-content/uploads/old_testdroid/2016/05/Selection_027.png)
 
**Dashboard** links back the landing page where summary of projects, test runs as well as update of recent changes in Testdroid Cloud will be shown.
 
**Projects** links to project management view where all user's projects can be managed.
 
**Reports** links to reports view where users can create reports of
projects and test runs.
 
**Device Groups** links to devices view where users can create their own
device groups.
 
**Manual Testing** opens Bitbar Testdroid Cloud's Manual Testing feature wherein user
can manually access any Bitbar Testdroid Cloud device.
 
## Test success summary
 
The **Test success summary** view shows the 5 recent projects with all done test runs with the success ratios. In this view, users can see a glance of their test run success as percentages and use the view as an instant link to the test runs. By clicking the specific test run chart user will be redirected to the test run view.
 
![](http://docs.testdroid.com/assets/user-manuals/dashboard_summary_success.png)
 
## Overall success
 
The **Overall success** view presents the success of projects combining all test runs in the context of time.  The execution date is shown on X axis and success ratio on Y axis.
 
![](http://docs.testdroid.com/assets/user-manuals/dashboard_overall_success.png)
 
Users can filter out certain projects by clicking the project name below the chart. The chart will automatically scale accordingly showing the execution dates and success ratio of remaining projects.
 
## New devices
 
The **New devices** view shows the latest devices added in Testdroid Cloud device selection. By clicking any of devices shown in this view, user will be instantly directed to the Device group creation view.
 
![](http://docs.testdroid.com/assets/user-manuals/device_groups.png)

## Projects

Under **Projects** view users are able to create, remove and manage their projects.  By clicking '+' button new projects can be created after the type of project is selected. The types of projects are: Android, iOS UI Automation, Android UIAutomator, Calabash Android, and Calabash iOS.

**NOTE!** Appium projects are generated on the fly and automatically detected by Testdroid Cloud. These projects cannot be created manually in this view.

![](http://docs.testdroid.com/assets/user-manuals/projects_projects.png)

On the right hand side, users can create project specific test runs, reports or share projects with other valid Bitbar Testing Cloud user accounts.
 
In test run section users can edit, insert tags or delete test runs. The view also shows the percentage of successful test runs, success of tests, the status of test run (how many devices have been finalized the test run), date and time information, as well as application specific information (e.g. the name of test and application file).

## Test run / Overview

User can access **Test Run view** either by starting a test run or clicking any of older test runs is dashboard or projects view. In this view test run execution information, execution time as well as success of test runs is shown in summary type of perspective.

The Bitbar Cloud test run starts always with device cleaning (removing all content from devices, cleaning SD card and rebooting devices), followed by installation and launch of the app and tests.

The first widget in Test Run View is summary.

![Picture. Test run view summary -widget](http://docs.testdroid.com/assets/user-manuals/projects_run_overview.png)

Overall statuses

* Finished - No errors, everything went fine
* Finished with failures - finished but some of test cases failed.
* Finished with errors - finished but errors in test execution. This
  is for example application or device crash.

In addition to summary information you can download the application and test files as well as as all the log files.  You can also access Test Case and Screenshots comparison views from the Summary widget.

Test run view details -widget contains summary information for each device.

![Picture. Test run view details -widget](http://docs.testdroid.com/assets/user-manuals/projects_run_details.png)

On the top-right of the test run widget, user can filter data shown in widget. For example, user can filter passed, failed, excluded, and not executed devices for the widget.  More specific error of test execution from test run can be seen when mouse is hovered on the top of red colored error message.  User can focus on each device run by clicking the device row.  User can open all device runs by clicking "Show all X devices" where X indicated the number of used devices in the test run.  User can also retry the test run for visible devices.

![Picture. Retry.](http://docs.testdroid.com/assets/user-manuals/projects_retry_listed.png)

**Note!** Previous test run information for the device will be
  overwritten!
 
## Device run details / Test cases
 
After clicking any row on test run view, user is directed to view
generic information about tests is shown. By selecting the name of
test (presented either as green/success of red/failure) the test steps
will be shown. User can also filter successful test runs by clicking
the eye icon on the top-right corner.

![](http://docs.testdroid.com/assets/user-manuals/projects_test_steps.png)

## Device run details / Screenshots
 
The Screenshots view shows all captured screenshots during the selected test. The number on the right-top corner of each screenshot indicates the step when screenshot was taken. For example, test run may have 22 steps. Each step will include a screenshot and if the step includes multiple screenshots, those are named as "number of step"."sub-number".  (e.g. 6.1, 6.2).

![](http://docs.testdroid.com/assets/user-manuals/projects_run_details_screenshots.png)

User can download all captured screenshots by clicking Download screenshots on the top right-corner of the widget.

## Device run details / Performance
 
The Performance view provides details of the test run for CPU and memory usage.  User can click any given step/time to get more specific information about resource consumption.

![](http://docs.testdroid.com/assets/user-manuals/projects_run_details_performance.png)

The performance log can be also downloaded by clicking the Download performance log button on the top right-corner of the widget.


## Device run details / Logs

The log view provides line-by-line information about the test run. It can be configured with types of information user wants to investigate and show in Logs view. Available configurations are: Info, Debug, Warning, Error, Assert and Verbose.

![](http://docs.testdroid.com/assets/user-manuals/projects_run_details_logs.png)

## Device run details / Device files
 
If the test or device run includes additional files those can be reviewed and download from this view. For example, if test run generates additional logs, users can get those files through this view after the test run is completed.

![](http://docs.testdroid.com/assets/user-manuals/projects_run_details_device_files.png)

All additional files can be downloaded by clicking Download all files button on the top right-corner of the widget.
 
## Screenshot comparison

The **Screenshot Comparison** view makes it easy to compare captured screenshots from every test run.
 
Users can select screenshots from dropdown menu that gets automatically shown on each device in the test run. Screenshots can be browsed also with arrow button on the top right-corner of the widget. For full-screen mode, user can click Full screen button and for downloading all screenshot Download screenshots button.

![](http://docs.testdroid.com/assets/user-manuals/projects_run_details_sc_comparision.png)

## Reports

The **Reports** view provides users a way to generate reports of their test runs, including key metrics or even full details of each test runs.
 
For example, user can select the project, test run, report type and report format, and the report will be automatically generated for user. It is also possible to download the report in different formats (PDF, HTML, CSV).

![](http://docs.testdroid.com/assets/user-manuals/reports.png)

The following steps will help users to create reports regarding their needs:

1. **Specify the report type.** After selecting the reports tool, the
first step is to specify the report type. Users can choose different
report types from the dropdown list placed in the upper left part of
the module. The report type list is divided into two parts: "Projects"
(reports for projects) and "Test runs" (reports for test runs). After
you select an option in this list the values in the other two
drop-downs menu will be updated accordingly.

2. **Choose the data source.** When user have specified the type of
report, user can choose from which of the projects/test runs user
wants to generate the report.

3. **Specify report format.** In the last drop-down menu you can choose
your preferred format (PDF, HTML or CSV).

4. **Preview window.** When user starts the reports module the preview
window is hidden. Users can activate the preview window by clicking
the text "Change selected values or click this text to refresh
preview" or by changing values in the drop-down lists. Thanks to the
preview window users can review reports before downloading them. The
preview window refreshes after every change is made.

5. **Downloading reports.** Last, when users are happy with their
reports, they can download the selected report by clicking the
"Download report" button.

## Device groups

Bitbar Testing Cloud enables its users to create a specific device groups that are used to point out on which devices tests are executed. The device group configuration can be found under the main menu - **Device Groups**.
 
Creation of a device group starts by giving a name for device group. After this, user needs to select either to be created device group is Android or iOS. Note that device groups can include devices from either platform, not both. By clicking **Create group** the device group will be created.
 
Users can include devices in device groups by selecting device separately on the left-hand side's browsing menu. After selection, user can drag and drop devices to newly created device group on the right-hand side.  The filter options on the left-hand side, for example, OS versions, API levels, CPUs and so on can be used to browse specific devices for selection.
 
![](http://docs.testdroid.com/assets/user-manuals/device_groups.png)
 
The other alternative for creating device groups is to select all desired devices on the left-hand side widget and clicking '+' on top of that widget. User can then configure more specific details - e.g. name - on the right-hand side widget.
 
The third way to configure device groups is enabled by clicking existing device group on the right-hand side widget. Devices included in the specific group will be shown and user can remove and add devices accordingly.

## Device logs
 
The **device logs** for Manual Testing session will show live log details
next to the Manual Testing session widget.

![](http://docs.testdroid.com/assets/user-manuals/interactive_device_logs.png)
   
## Screenshots
 
The **Taken screenshots** view shows all captured screenshots during the
Manual Testing session.

All captured screenshots can be downloaded by clicking Download
screenshots button on the top right-corner of the widget.

![](http://docs.testdroid.com/assets/user-manuals/interactive_screenshots.png)
