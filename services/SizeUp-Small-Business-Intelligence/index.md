---

copyright:

  years:  2017

lastupdated: "2017-10-18"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

<!-- This template is for getting started with a Bluemix service. It is a task template intended to document productive use of the service. It is not intended for discovery and conceptual information.  -->

<!-- The name of this file should remain index.md.
Please delete out content examples and coding that you are not using for your service. -->

# Getting started with <service_short_name>
{: #gettingstarted}
<!-- Provide an appropriate ID above -->

<!-- Short description: REQUIRED

See usage examples below, or read the full docs at [Sizeup developer docs]().

This service can be accessed via javascript in the browser or in node.

## Example: SizeUp from browser code

To run SizeUp entirely in a browser application, reference the script directly from our servers using your product key. For example, here we look up the average revenue of Shoe Repair businesses in Chicago and its county.

#### Installation

    <script src="https://api.sizeup.com/js/?callback=onLoadSizeup&apikey=YOUR_PRODUCT_KEY_HERE"></script>

#### Use

    <script type="text/javascript">
      let report = {};

      ////// Look up industry and place objects //////
      function onLoadSizeup() {
        sizeup.data.findIndustry(
          { term: "shoe repair" },
          function(industries) { report.industry = industries[0]; onLoadIndustries(); },
          console.error);
      }
      function onLoadIndustries() {
        sizeup.data.findPlace(
          { term: "chicago" },
          function(places) { report.place = places[0]; onLoadPlaces(); },
          console.error);
      }
      function onLoadPlaces() {

        ////// Get citywide data //////
        sizeup.data.getAverageRevenue(
          { geographicLocationId: report.place.City.Id, industryId: report.industry.Id },
          function(data) { alert(
            "Average revenue of " + report.industry.Name
            + " businesses in " + report.place.City.Name
            + ": $" + data.Value);
          },
          console.error);

        ////// Get countywide data //////
        sizeup.data.getAverageRevenue(
          { geographicLocationId: report.place.County.Id, industryId: report.industry.Id },
          function(data) { alert(
            "Average revenue of " + report.industry.Name
            + " businesses in " + report.place.County.Name
            + " County: $" + data.Value);
          },
          console.error);
      }
    </script>

Outputs:

    Average revenue of Shoe & Boot Repairing businesses in Chicago: $109571
    Average revenue of Shoe & Boot Repairing businesses in Cook County: $96127

## Example: SizeUp from Node.js

The `sizeup-api` npm package allows both callback coding (as in the above example) or ES6 Promise coding, as shown below. Here we look up the revenue per capita of Coffee Shops in Oakland and its county.

#### Installation

    npm install sizeup-api

#### Use

    const sizeup = require("sizeup-api")({ key:YOUR_PRODUCT_KEY_HERE });

    ////// Look up industry and place objects //////
    Promise.all([
      sizeup.data.getIndustryBySeokey("coffee-shops"),
      sizeup.data.getPlaceBySeokey("california/alameda/oakland-city"),
    ]).then(([industry, place]) => {
      Promise.all([
        ////// Get citywide data //////
        sizeup.data.getRevenuePerCapita({geographicLocationId: place.City.Id, industryId: industry.Id}),
        ////// Get countywide data //////
        sizeup.data.getRevenuePerCapita({geographicLocationId: place.County.Id, industryId: industry.Id}),
      ]).then(([city_data, county_data]) => {
        console.log(
          `Revenue per capita of ${industry.Name} `
          + `businesses in ${place.City.Name}: `
          + `${city_data.Value}` );
        console.log(
          `Revenue per capita of ${industry.Name} `
          + `businesses in ${place.County.Name} County: `
          + `${county_data.Value}` );
      })
    }).catch(console.error);

Outputs:

    Revenue per capita of Coffee Shops businesses in Oakland: $86
    Revenue per capita of Coffee Shops businesses in Alameda County: $114

## Other languages

The Node binary allows you to use Sizeup software from languages other than Node, by launching shell commands. For example:

#### Installation

    npm install -g sizeup-api

#### Use

    $ export SIZEUP_KEY=YOUR_PRODUCT_KEY_HERE
    $ bin/sizeup.js findPlace '{"term": "austin, tx"}'
    ...
      "DisplayName": "Austin, TX (Travis County - City)",
      "City": {
        "Id": 104971,
    ...
    $ bin/sizeup.js findIndustry '{"term": "burger"}'
    [
      {
        "Id": 8524,
        "Name": "Burger Restaurants",
    ...
    $ bin/sizeup.js getAverageRevenue '{"geographicLocationId": 104971, "industryId": 8524}'
    {
      "Value": 1537200,
      "Median": 1481000,
      "Name": "Austin, TX"
    }

Read more at [Sizeup developer docs].

[Sizeup developer docs]: https://www.sizeup.com/developers/documentation













The short description section should include one to two sentences describing why a developer would want to use your service in an app. This should be conversational style. For search engine optimization, include the service long name and "Bluemix". Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.

Examples: -->

<service_name> is a... -OR-
With <service_name>, you can...  -OR-
Use <service_name> to...
{:shortdesc}

<!-- If overview content is required, do not include it here. Put it in a separate "## About" section below the task section. -->

<!-- Task section: REQUIRED
The task section includes steps to integrate the service into the app.  
- With task-based, technical information, reduce the conversational style in favor of succinct and direct instructions.
- DO include the basic, most-common-use scenario steps to use the service or integrate it into the app. 
- DO NOT include steps to add the service from the Bluemix catalog; we assume that the user already took steps in the UI to add the service. 
- DO include code snippets in all languages that can be copied, as well as VCAP service info.  
- For additional tasks like configuring, managing, etc., add a task section (## Gerund_task_title) below the task section or "About" section if used. Use a task title such as "Configuring x", "Administering y", "Managing z". -->

<!-- You can include an optional prerequisites paragraph for any prerequisites to be met before integrating the service. For example: -->

Before an application developer can... the administrator must ...

<!-- Include a sentence to briefly introduce the steps. Examples: -->

To integrate your app with the service, complete these steps: -OR-
To get up and running quickly with this service, follow these steps: -OR-
Complete these steps to get started with the BigInsights service:

<!-- Use ordered list markup for the step section. For code examples: 
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

1. List step 1 to integrate app with the service.
2. List step 2 to integrate app with the service.

	```
	Copyable example for this step. 
	This example might be multiline code
	to copy into a file. 
	When displayed in the doc framework, 
	it will have a copy button on the right.
	The user can click to copy the example 
	so they can paste it into their code editor.
	```
	{: codeblock}

3. List step 3 In this step, <introduce the example that follows>.

	```
	my command -and -options
	```
	{: pre}

4. List step 4
	```
	This is a bunch of output from
		a command or program I ran
			and it can run lots of lines
			and the doc framework will show it as 
			output with no copy button.
	```
	{: screen}



<!-- Related links section: still REQUIRED but moved to toc file (in your same folder).  Edit there.
-->