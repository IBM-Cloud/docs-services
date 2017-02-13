---

copyright:

  years: 2016

lastupdated: "2016-10-13"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Getting started with Mapbox maps
{: #gettingstarted}

Mapbox APIs enables you to create, share, and interact with maps on your web and mobile applications on Bluemix. Start with a basemap built by our cartographers or create your own custom style in [Mapbox Studio](www.mapbox.com/studio), then add your own spatial data, embed the map in your app, and interact using [Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/api/).

To get started with Mapbox APIs on Bluemix:

1. If you don't already have a Mapbox account, [sign up for one here](https://www.mapbox.com/studio/signup/?path=%2Faccount%2Fapps%2F){:new_window}. Note: Commercial applications, including paid and private applications, require a Mapbox Premium or Enterprise account.
2. Login to [Mapbox Studio](https://www.mapbox.com/studio/){:new_window}. Record your Mapbox username and default access token from the homepage.
    ![](https://cl.ly/261A3p2P1i3S/download/Image%202016-10-13%20at%205.03.20%20PM.png)
3. Fill out your Mapbox account name and Mapbox default access token on Bluemix.
4. Grab a default basemap URL or create a new map style with [Mapbox Studio](https://www.mapbox.com/studio/styles/){:new_window}. Check out our [getting started with Mapbox Stuido guide](https://www.mapbox.com/help/getting-started-mapbox-studio-1/){:new_window} for a kickstart.
5. Collect the `style URL` and `access token` from the map style you created with Mapbox Studio.
    ![](https://cl.ly/140D1f2I0P1v/download/Image%202016-10-13%20at%205.09.42%20PM.png)
6. Initialize the map in your application using your `style URL` and `access token` with [Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/example/custom-style-id/){:new_window}. Replace `YOUR_ACCESS_TOKEN` and `YOUR_STYLE_URL` in the javascript below with your `style URL` and `access token`.

	```
    <html>
    <head>
    <meta charset='utf-8' />
    <title></title>
    <meta name='viewport' content='initial-scale=1,maximum-scale=1,user-scalable=no' />
    <script src='https://api.tiles.mapbox.com/mapbox-gl-js/v0.26.0/mapbox-gl.js'></script>
    <link href='https://api.tiles.mapbox.com/mapbox-gl-js/v0.26.0/mapbox-gl.css' rel='stylesheet' />
    <style>
        body { margin:0; padding:0; }
        #map { position:absolute; top:0; bottom:0; width:100%; }
    </style>
    </head>
    <body>

    <div id='map'></div>
    <script>
    mapboxgl.accessToken = 'YOUR_ACCESS_TOKEN';
    var map = new mapboxgl.Map({
        container: 'map', 
        style: 'YOUR_STYLE_URL',
        center: [-77.38, 39],
        zoom: 3
    });
    </script>
    </body>
    </html>
	```
	{: pre}

# Related Links
{: #rellinks notoc}

## Tutorials and Samples
{: #samples}

1. [Getting Started with Mapbox Studio](https://www.mapbox.com/help/getting-started-mapbox-studio-1/){:new_window}
2. [Build a Store Locator with Mapbox GL JS](https://www.mapbox.com/help/building-a-store-locator/){:new_window}

## SDK
{: #sdk}

* [Mapbox GL JS SDK](https://www.mapbox.com/mapbox-gl-js/api/){:new_window}

## API Reference
{: #api}

* [Mapbox API](https://www.mapbox.com/api-documentation/#styles){:new_window}

## Compatible Runtimes
{: #buildpacks}

* [Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/api/){:new_window}

## Related Links
{: #general}

* [Mapbox GL JS Examples](https://www.mapbox.com/mapbox-gl-js/examples/){:new_window}
* [Mapbox Data Driven Style Tutorial](https://www.mapbox.com/help/gl-dds-ref/){:new_window}
