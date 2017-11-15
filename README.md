# GeoServer ArcGIS Rest API

This plugin provides an ArcGIS REST compatibility API.

## Installation

Drop all the jar files in the distribution into the WEB-INF/lib directory
of your GeoServer and restart.

## Usage

Currently basic FeatureServer and MapServer functionality work. Each GeoServer workspace is considered
an ArcGIS "service" for the purposes of the API. ArcGIS URLs look like this in GeoServer:

http://localhost:8080/geoserver/gsr/services/topp/MapServer/
http://localhost:8080/geoserver/gsr/services/topp/FeatureServer/

Where topp is the workspace name.

## Not Supported

Notable features currently unsupported:

- Non-geospatial filters
- Identify feature
- Dynamic layer definitions

## Usage Notes
When using the official JS API, CORS detection does not work correctly. You will need to add
your server manually to the list of CORS enabled servers:

```javascript
    require(["esri/config"], function (esriConfig) {
        esriConfig.request.corsEnabledServers.push("localhost:9191");
    });
```