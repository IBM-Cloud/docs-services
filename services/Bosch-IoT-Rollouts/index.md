---

copyright: "Bosch Software Innovations GmbH, Germany"

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

# Getting started with Bosch IoT Rollouts
{: #gettingstarted}

Bosch IoT Rollouts is a domain independent back-end solution for rolling out software updates to constrained edge devices as well as more powerful controllers and gateways connected to IP based networking infrastructure. Devices can connect to the Rollouts server either directly through an optimised interface or indirectly through federated device management servers.

{:shortdesc}

Create an account at [Bosch IoT Rollouts](https://www.bosch-iot-suite.com/rollouts/) and order the service instance. Bluemix applications can integrate with the service in order to:

- Manage software updates and/or the repository by integrating with [Management API](https://docs.bosch-iot-rollouts.com/documentation/developerguide/apispecifications/managementapi.html) or
- Plug into Rollouts for custom device connectivity by integrating with [Device Management Federation API](https://docs.bosch-iot-rollouts.com/documentation/developerguide/apispecifications/devicemanagementfederationapi.html)

To get up and running quickly with this service, we recommend to take a look at the client examples of the [Eclipse hawkBit™](https://github.com/eclipse/hawkbit) project as Bosch IoT Rollouts is fully API compatible to it.

1. Decide about the role your Bluemix application has in context of Bosch IoT Rollouts (i.e. DMF or Management API integration)
2. In case of DMF integration we recommend to take a look [this guide](https://docs.bosch-iot-rollouts.com/documentation/developerguide/guides/gettingstartedservice.html) to get started. You will need to fill the `amqpuri` variable in your service binding.
3. In case of Management API you app can leverage the tenant, username and password variable in your service binding.
4. Note that both for [Management API](https://docs.bosch-iot-rollouts.com/documentation/developerguide/apispecifications/managementapi.html) as well as [Device Management Federation API](https://docs.bosch-iot-rollouts.com/documentation/developerguide/apispecifications/devicemanagementfederationapi.html) the compatability to Eclipse hawkBit™ allows you to leverage all their client examples, API models as well as [3rd party client implementations](https://docs.bosch-iot-rollouts.com/documentation/introduction/ecosystem.html).