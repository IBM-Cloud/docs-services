---

copyright:

  years: 2017

lastupdated: "2016-02-28"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with XpertRule Decision Automation for node-RED
{: #gettingstarted} 
*Last updated: 28 Feb 2017*

XpertRule is a global leader in next generation Decision Automation services for IoT products and solutions. Their service, Decision Automation for node-RED, enables complex decision logic to be maintained externally to node-RED, enabling more effective governance and configuration of the overall solution. Decision Automation nodes can be built, visualized, tested and modified quickly and easily, before being deployed into a node-RED node in a matter of seconds.

IoT applications often require some level of automated decision making – to make sense of the data being monitored, to detect anomalies, make real-time calculations and to decide on the most appropriate next action. To achieve this in node-RED alone is not always feasible, especially when the decision logic is complex and scales to multiple scenarios (e.g. in a multi-asset IoT use case).
{:shortdesc}

## Getting Started
This document will show how quickly (20 minutes or less) a knowledge base application can be developed and deployed into a node-RED flow for the purpose of making decisions/outcomes on live IOT data. First, you’ll learn how to find, launch and use the Decision Automation for node-RED on Bluemix.

The first step is to login to Bluemix and choose the Decision Automation for node-RED service, located in Catalog under Services / Internet of Things. Next, click on Decision Automation for node-RED and create a free plan. Then, open the Dashboard. When you add a Decision Automation for node-RED service into the Bluemix dashboard, you are directed to the Decision Author launch screen

## Demo
Next, we’ll demonstrate how to get started with Decision Author. To do this, we have built a demo which illustrates how you can quickly develop and deploy a knowledge base application.

- Premise: Our demo is a fictional solution for monitoring the health of a household plant. Hopefully this will demonstrate the speed at which you can add complex domain knowledge to node-RED flows (without coding) to inspire you to go and create bigger and better solutions.

- Hardware: EnviroPhat – collects sensor data (Compass, Light, Pressure and Temp) and Raspberry Pi

- Technologies: node-RED (to wire everything together) and Decision Author (to create a knowledge base to drive decision &amp; outcome

## Step 1
We start in Decision Author by creating 4 trees which provide a semantic representation of the underlying sensor values – Compass, Light, Pressure and Temp. We attribute values and outcomes to each tree and, in the case of Pressure, we also build in a formula to convert the sensor reading from Pascals to Hectopascals.

In each of the 4 steps, there is an accompanying video. While there is no audio in the videos, each shows you the steps you need to take.

[his video is a little over 11 minutes.](https://www.youtube.com/watch?v=iXw0lcRnJSA&amp;feature=youtu.be)

## Step 2
Next we create a truth table which lists all the possible outcomes from our 4 trees. The next stage is to apply industry/domain knowledge using an expert (we didn’t have a plant growing expert in our office on the day we produced this demo so we’ve improvised) to select the various decision examples/outcomes (48 rows in total) that will be fed back into the node-RED flow.

[This video is a little over 4 minutes.](https://www.youtube.com/watch?v=z5zoEIomgQ8&amp;feature=youtu.be)

## Step 3
Once set, we now induce a decision tree from the examples/outcomes.

[This video is only 25 seconds in length](https://www.youtube.com/watch?v=PtgHa0lFio8&amp;feature=youtu.be)

We now have knowledge represented in a readily maintainable form for the purpose of making decisions in the quickest and most consistent way.

## Step 4
All that’s left is to simply deploy our knowledge into a node-RED node using copy and paste. Exit Decision Author and open a node-RED flow (return to the Decision Author Launch Screen at any time to modify / update and re-deploy your knowledge).

[This video is 46 seconds in length](https://www.youtube.com/watch?v=w9GWBqOhbH0&amp;feature=youtu.be)

## Testing
Another big advantage of building knowledge in Decision Author is that you can test your logic/outcomes before you deploy into node-RED. This short video shows you how:

[This video is just under 2 mins](https://www.youtube.com/watch?v=mb8gxwwgJjo&amp;feature=youtu.be)

## Key Benefits
- Decision Automation is a key enabler of Industrial IoT use cases, such as condition monitoring, anomaly detection and process optimization. Now that you have completed the demo, it is important that you understand the benefits of using XpertRule’s Decision Author:
- Rapid development – The graphical programming UI and intuitive Decision Authoring are up to 30x faster than standard scripting / development.
- Accessible to non-coders – Domain Experts, Business Analysts, Process Owners with no coding experience can build and maintain complex decision logic.
- Rich Representation of Knowledge – Decision Flows, Decision Trees, Decision Tables, Tree Induction, Formula Editor and Scripting.
- peed of Deployment – Simply copy and paste your knowledge applications into a node-Red node.

## Next steps
Install an XREngine node so you can copy and paste knowledge straight from Decision Author into node-RED:
- Open your Node-RED flow editor.
- From the burger menu (top right), select Manage palette.
- To the left of the screen, click the install tab and search for XREngine.
- Install the node-red- contrib-xrengine node and click done.
- Drag and drop into your flow as appropriate.