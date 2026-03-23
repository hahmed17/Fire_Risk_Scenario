# Prerequisites
- Python
- GDAL
- At least 4 CPUs (to run FARSITE simulations)


# Wildfire Commons Resources
- **FARSITE.** The `farsite` directory contains the executable files and source code required to configure and run a FARSITE fire spread simulation.
- **Forest landscape data.** The `Forest` directory contains the landscape and tree data (in `.tif`, `.geojson`, and `.txt` format) that are used as inputs to the FARSITE simulation.
- **Ignition coordinates.** The given latitude/longitude coordinate for this location is **N 38° 54.081' W 120° 1.837'**, circa South Lake Tahoe, CA, USA. 
- **Weather parameters.** Parameter values for wind, air, and climate conditions are provided as inputs to the FARSITE simulation.



# Data Transformation: `data_transformation.ipynb`
- Derives landscape raster bands in `.tif` file format
- Projects landscape layers to EPSG:5070
- Aligns and rescales layers to the elevation grid
- Converts `.tif` bands to ASCII rasters (`.asc`)
- Compiles all layers into `Forest_LCP_Outputs/landscape.lcp` using `farsite/lcpmake` executable
- Writes the EPSG:5070 projection header into the `.lcp` file


# Intermediate Data Outputs

`Forest_LCP_Outputs`
- Eight `.tif` raster files
- Eight `asc` files (with corresponding `.prj` and `.xml` files)
- `landscape.lcp` file compatible with FARSITE input requirements


# FARSITE Fire Spread Simulation: `farsite_simulation.ipynb`
- Builds an ignition polygon around the given ignition coordinate
- Runs FARSITE iteratively in 30-minute steps for 4 hours
- Each step's output perimeter becomes the ignition polygon for the next step
- Plots all perimeters and prints area growth statistics over time
- Exports all perimeters to `fire_output_geojsons/perimeters.geojson`



# Final Model Outputs: `fire_output_geojsons`
This directory contains the FARSITE prediction geometries as Polygon objects in `perimeters.geojson`.

