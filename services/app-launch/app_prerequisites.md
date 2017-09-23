---

copyright:
 years: 2017

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Prerequisites
{: #prerequisites}
Last updated: 23 September 2017
{: .last-updated}


## Creating an App Launch service instance
{: #prerequisites_1}

1. In the [IBM Bluemix Catalog](https://console.ng.bluemix.net/catalog/), click **Mobile** > **App Launch**.
2. Provide a Service name and a Credential name.
3. Choose to connect to other existing apps, or leave it unbound.
4. Click **Create**.


You can choose to create either a bound service or an unbound service. Bound services are connected to other Bluemix apps, while unbound apps are standalone and not connected to other apps. App Launch service apps are unbound by default.


## Creating a feature
{: #prerequisites_2}

This is a mandatory prerequisite for creating a Feature Toggle or an engagement. Complete the following steps:

1. Click **Features and Metrics** > **Create Feature**.

2. Update the Create New Feature and Metrics form with an appropriate feature name and description. You can also define the feature properties and add metrics to measure the impact of your engagement.

3. Click **Create**. The new feature now appears on the Features and Metrics panel. 
![New Features](images/feature_creating.gif)

4. To enable a feature to be used as an engagement, click the Feature that you have created.

5. In the Feature Details window, choose to Update Status of your feature to **Ready**.
![Feature Details](images/feature_details.gif)

6. Click **Update Status**.

7. The feature is now ready to be used.
![Feature ready to be used](images/feature_multiple_1.gif)

You can now create an engagement using the [Feature Toggle](app_feature_message.html) option.

## Creating an audience
{: #prerequisites_2}

This is a mandatory prerequisite for creating an engagement. Complete the following steps:

1. Create an audience attribute. 

	a. Click **Audience** > **Create Audience Attribute**.

	b. Provide the following values:

	- **Name**: Provide an appropriate name for the attribute.
	- **Description**: A brief description on the attribute.
	- **Type**:	Choose the attribute type.
	- **Allowed values**: Enter the attribute values that you would want to use.

	![Audience attributes](images/audience_attribute_creation.gif)

	You can choose to create multiple audience attributes, as listed in the following image, based on your requirement.
	
	![Audience attributes](images/audience_attributes.gif)


2. Create an audience.

	a. Click **Create Audience**.

	b. Provide an appropriate name and description on the New Audience window.

	c. Select an attribute, and click **Add**.

	![Audience attributes](images/audience_platforms.gif)

	d. Choose the required options from the listed attributes.

	e. Click **Save**.

You can now create an engagement using the [Messaging](app_feature_message.hmtl) option.