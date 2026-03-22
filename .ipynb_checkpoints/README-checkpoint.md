# Requirements
 1. At least 4 CPUs
 2. Dependencies installation:
```
chmod +x install_packages.sh
./install_packages.sh
```



The Forest landscape directory contains the following data:
    <city name>_depth.tif : 1 band raster file of surface fuel depth [meters] 
    <city name>_fbfm13.tif : 1 band raster file of Anderson fuel model [int] 
    <city name>_generated_buildings_fireprops.geojson : geojson containing synthetic building polygons from a separate collaborator
    <city name>_moist.tif : 1 band raster file of surface fuel moisture [dec] 
    <city name>_rhof1.tif : 1 band raster file of 1 hour surface fuel loading [kg/m^2]    
    <city name>_rhof10.tif : 1 band raster file of 10 hour surface fuel loading [kg/m^2]     
    <city name>_rhof100.tif : 1 band raster file of 100 hour surface fuel loading [kg/m^2] 
    <city name>_SAV.tif : 1 band raster file of fuel surface area to volume [1/m] 
    <city name>_Treelist.geojson : geojson containing tree data including 
        lat/lon, height (HT) [m], 
        canopy base height (CBH) [m],
        maximum canopy diameter (DIA) [m],
        height to maximum canopy diameter (HT_TO_DIA) [m],
        canopy bulk density (CBD) [kg/m^3],
        canopy moisture (MOIST) [dec],
        fine fuel size scale (SS)
    <city name>_Treelist.txt : text file containing the same data as <city name>_Treelist.geojson in txt format
    roads.geojson : geojson containing road network
    <city name>_elevation.tif : 1 band raster file of elevation from USGS DEM products 