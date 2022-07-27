# 2D Map Viewer With Leaflet.js 

2D map viewers created using the Leaflet.js library with a small set of WMS and raster data hosted on GeoServer.


## Geoserver to Leaflet Workflow

 * Takes in WMS, WFS, and raster data hosted on GeoServer. 
 * Example: Using WMS data from GeoServer:
 ```
var wms_blocks = new L.tileLayer.wms(
        "http://virtualblackcharlotte.net/geoserver/Charlotte/wms",
        {
          layers: "Charlotte:Blocks",
          format: "image/png",
          transparent: true,
          opacity: 0.5
        }
      ).addTo(map);
```

## Example Maps in index.html

### Toggle Layers
Multiple WMS layers, one raster layer, and one base OpenStreetMap can be toggled on and off using Layer control (can toggle on and off the raster and WMS layers, but not the basemap) 
```
var layerControl = L.control.layers(basemap, overlayMaps).addTo(map);
```
### Map Swipe with Toggle WMS layers 
Left is the geo-referenced raster data and right is the OpenStreetMap. The traced WMS layer is displayed with 0.5 opacity and can be toggled on and off
Credit: http://bl.ocks.org/wboykinm/b90873f4015fd8a8759e

### Colored WMS Layers using QGIS SLD files 
.shp file from ARCGIS Pro is exported and imported into QGIS. Using QGIS symbology and export as SLD file. Uploading directly to GeoServer and applied to WMS layers.

### Colored WMS Layers with Toggle Layer Control. 
The color coordinates with the feature classes. For this example, only buildings can be toggled on and off based on feature attribute (Dilapidated, Major Repair, etc). 
