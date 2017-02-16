---

copyright:

  years: 2017

lastupdated: "2016-02-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with XpertRule Decision Automation for node-RED
{: #gettingstarted} 
*Last updated: 16 Feb 2017*

XpertRule Decision Author for Node-RED is a tool for developers to rapidly add complex decision and analytics automation to Node-RED flows. XpertRule Decision Author is ideal in manufacturing, utilities, aerospace, automotive sectors and anywhere that requires automation of complex decisions, calculations, diagnosis or root-cause analysis. It's simple to deploy as a Node-RED node and execute wherever Node-RED can be run: edge or cloud.
{:shortdesc}

## Overview

Add Decision Automation to your node-RED flows!

IoT applications often require some level of automated decision making – to make sense of the data being monitored, to detect anomalies, make real-time calculations &amp; to decide on the most appropriate next action.

To achieve this in node-RED alone is not always feasible, especially when the decision logic is complex &amp; scales to multiple scenarios (e.g. in a multi-asset IoT use case).

Decision Automation for node-RED enables complex Decision logic to be maintained externally to node-RED, enabling more effective governance &amp; configuration of the overall solution. Decision Automation nodes can be built, visualised, tested &amp; modified quickly &amp; easily, before being deployed into a node-RED node in a matter of seconds.

## Key Benefits
Decision Automation is a key enabler of Industrial IoT use cases such as condition monitoring, anomaly detection &amp; process optimisation. The benefits of using XpertRule’s Decision Author are:
    
- Rapid development – The graphical programming UI &amp; intuitive Decision Authoring is upto 30x faster than standard scripting / development.
- Accessible to non-coders – Domain Experts, Business Analysts, Process Owners with no coding experience can build &amp; maintain complex decision logic
- Rich Representation of Knowledge – Decision Flows, Decision Trees, Decision Tables, Tree Induction, Formula Editor &amp; Scripting
- Speed of Deployment – Simply Copy &amp; Paste your knowledge applications into a node-Red node

## Intro to Decision Author
In this section we will provide details on how to find, launch &amp; use our service.

The first step is to login to Bluemix &amp; choose the Decision Automation for node-RED service, located in Catalog under Services / Internet of Things

Next, click on Decision Automation for node-RED &amp; create a free plan Then, open the Dashboard. When you add a Decision Automation for node-RED service into the Bluemix dashboard, you are directed to the Decision Author launch screen.

Next we’ll demonstrate how to get started with Decision Author. To do this we will show you how to build a knowledge base and deploy into a node-RED flow as part of a complete solution. For this demo we are working on the premise that our knowledge base is being used to drive decisions, calculations and outcomes on IoT sensor data as part of a fictional plant monitoring solution.

Hopefully this will demonstrate the speed at which you can add complex domain knowledge to node-RED flows (without coding) to inspire you to go &amp; create bigger &amp; better solutions

## Step 1
We start in Decision Author by creating 4 trees which provide a semantic representation of the underlying sensor values - Compass, Light, Pressure and Temp. We attribute values &amp; outcomes to each tree &amp; in the case of Pressure we also build in a calculation to convert the sensor reading from Pascals to Hectopascals

Watch (11.08 mins)
[Watch (11.08 mins)](https://www.youtube.com/watch?v=iXw0lcRnJSA&amp;feature=youtu.be)

## Step 2
Next we create a truth table which lists all the possible outcomes from our 4 trees. The next stage is to apply industry/domain knowledge using an expert (we didn’t have a plant growing expert in our office on the day we produced this demo so we’ve improvised) to select the various decision examples/outcomes (48 rows in total) that will be fed back into the node-RED flow.

[Watch (4.48 min)](https://www.youtube.com/watch?v=z5zoEIomgQ8&amp;feature=youtu.be)

## Step 3
Once set, we now induce a decision tree from the examples/outcomes.

[Watch (25 secs)](https://www.youtube.com/watch?v=PtgHa0lFio8&amp;feature=youtu.be)

We now have knowledge represented in a readily maintainable form for the purpose of making decisions in the quickest &amp; most consistent way.

## Step 4
All that’s left is to simply deploy our knowledge into a node-RED node using copy &amp; paste. Exit Decision Author and open a node-RED flow (return to the Decision Author Launch Screen at any time to modify / update &amp; re-deploy your knowledge

[Watch (48 secs)](https://www.youtube.com/watch?v=w9GWBqOhbH0&amp;feature=youtu.be)

## Summary
This knowledge base took us less than 20 minutes to develop. Deploying the knowledge base into node-RED took a matter of seconds. We estimate a developer starting from scratch would take between 3-4 days to produce something similar.

## More Info:
How to install an XREngine node so you can copy &amp; paste knowledge straight from Decision Author into node-RED

- Open your Node-RED flow editor.
- From the burger menu (top right), select manage palette.
- To the left of the screen click the install tab &amp; search for xrengine.
- Install the node-red- contrib-xrengine node &amp; click done.
- Drag &amp; drop into your flow as appropriate

## About
XpertRule is a global leader in next generation Decision Automation services for IoT products &amp; solutions