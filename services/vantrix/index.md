{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Vantrix Transcoder for Bluemix
{: #gettingstarted}
*Last updated: 12 October 2016*

Vantrix Transcoder for Bluemix is a flexible and powerful transcoding service that you can use to adapt your single-rate VODs to multiple adaptive bitrate (ABR) outputs. It provides a complete transcoding workflow with support for various input/output formats (see About) as well as closed captioning. Vantrix Transcoder includes both an intuitive UI and a REST-based HTTP API. 
{:shortdesc}

## Setting up Vantrix Transcoder
To add the Vantrix Transcoder service using the command line, you need the Cloud Foundry CLI installed on your computer. Get it from [https://github.com/cloudfoundry/cli#downloads](https://github.com/cloudfoundry/cli#downloads). Once it’s installed, you'll be able to use the `cf` command from your command line interface.

To add Vantrix Transcoder service to your Bluemix application, follow these steps:
1. Set up the Bluemix API endpoint:
  ```
  cf api https://api.ng.bluemix.net
  ```
  {: pre}
		
2. Then log in to Bluemix with your Bluemix credentials:

  ```
  cf login
  ```
  {: pre}
		
3. Choose your organization and space, and you are ready to add the Vantrix Transcoder service. 
4. Now create a service instance in your selected space, for example:

  ```
  cf create-service vantrix-transcoder free mytranscoder01
  ```
 {: pre}
	
  where ‘vantrix-transcoder free’ is the service and 'mytranscoder01' is the service instance name. 

5. Bind your Vantrix Transcoder service instance to your application, for example:

  ```
  cf bind-service MyApp mytranscoder01
  ```
  {: pre}

  where 'MyApp' is your application and ‘mytranscoder01’ is your service instance.

6. Optionally, to show the service is bound to your application, use the `cf services` command.		
7. After Vantrix Transcoder service is bound to your application, the specific configuration of your Vantrix Transcoder service will appear in your VCAP_SERVICES environment variable. To list the details, use the `cf env` command followed by your application name, for example:

```
cf env MyApp
```
{: pre}
		
where 'MyApp' is your application.
		
The output will include something like this:
		
```
"VCAP_SERVICES": {
	"vantrix-transcoder": [
		{
		 "credentials": {
				"api_key": "7291dbcfe37cf478999b16476294c59e",
				"api_url": "https://cloud.vantrix.com/vta/v1",
				"dashboard_url": "https://cloud.vantrix.com/free?x-vta-key=7291dbcfe37cf478999b16476294c59e",
			 "sftp_password": "68e871ca5b994677ec1c8c2ab92c6b351a06ff49a3aedf85c11bfb07b6ec286e",
			 "sftp_url": "sftp://cloud.vantrix.com",
				"sftp_username": "4cldun4xx6omla84qmy9jwg8kq9pro"
			},
		 ...
```		 
{: screen}
	
The credentials block provides everything you need to use the Vantrix Transcoder service.
- **api_key**  -  your key for accessing the Vantrix Transcoding API
- **api_url**  -  the URL of the Vantrix Transcoding API
- **dashboard_url**  -  the URL of the Vantrix Transcoder UI
- **sftp_password**  -  your password for accessing your private storage for Vantrix Transcoder 
- **sftp_url**  -  the URL of your private storage for Vantrix Transcoder 
- **sftp_username**  -  your username for accessing your private storage for Vantrix Transcoder 
Note that the credentials are also available on the Account page of the VTA UI (at dashboard_url). 

To get started using the API to transcode your media files, please see the [API QuickStart](http://vantrix.com/wp-content/uploads/2016/06/VTA-QuickStart-v56.pdf){:new_window} and the [VTA API Specification](http://www.vantrix.com/wp-content/uploads/2016/04/Vantrix_Transcoding_API.pdf){:new_window}. 
# About Supported Formats and Codecs
The Bluemix Free Plan supports MPEG-TS and MP4 inputs and MPEG-TS, MP4 and HLS outputs with the following codecs: 
- MPEG-TS inputs with MPEG-2 or H.264 video codec and AAC, MP3 or MP2 audio codec
- MP4 inputs with H.264 video codec and AAC audio codec
- MPEG-TS outputs with MPEG-2, H.264 or H.265 video codec and AAC audio codec
- MP4 outputs with H.264 video codec and AAC audio codec
- HTTP Live Streaming (HLS) outputs with H.264 or H.265 video codec and AAC audio codec
	
# Related Links
{: #rellinks}

## Tutorials and Samples
{: #samples}

* [Vantrix Transcoding API QuickStart](http://vantrix.com/knowledgebase/Vantrix_Transcoding_API_QuickStart){:new_window}
* [Introducing Vantrix Transcoder User Interface](http://vantrix.com/knowledgebase/Introducing_Vantrix_Transcoder_User_Interface){:new_window}

## API Reference
{: #api}

* [Vantrix Transcoding API Specification](http://vantrix.com/knowledgebase/Vantrix_Transcoding_API){:new_window}

## Related Links
{: #general}

* [Vantrix Resources](http://vantrix.com/resources/){:new_window}
