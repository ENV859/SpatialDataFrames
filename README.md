# Working with Spatially Enabled DataFrames 

## Overview

The spatially enabled dataframe (a.k.a. "*spatial dataframe*", "*sdf*", or "*geodataframe*") is a Pandas dataframe with an additional column containing geometric data - exactly like the familiar feature classes we've been working with in ArcGIS. This set of notebooks explores various techniques for creating, analyzing, and visualizing spatial dataframes. In doing so, we delve into the components of geometric data in a dataframe (geometries, geoseries, and projections) as well as the various Python packages that are involved with working with these datasets, mainly *GeoPandas* and the *ArcGIS Python API*, but also the modules on which these packages are dependent: *Shapely*, *Fiona*, *PyProj*, *PyEPSG*, *GeoPy* and *MatPlotLib*. 

### 

### Behind the scenes: Python packages used in working with SDFs
#### Data handlers: Fiona or ArcPy
#### Data wranglers: Pandas
#### The geometry engine: Shapely or ArcPy
#### Projections: PyProj, PyEPSG, or ArcPy
#### Visualization: Matplotlib or ArcGIS API
#### Geocoders: geopy or ArcGIS API

## Resources
* http://geopandas.org/index.html
* https://developers.arcgis.com/python/guide/introduction-to-the-spatially-enabled-dataframe/
* https://esri.github.io/arcgis-python-api/apidoc/html/arcgis.features.toc.html#spatialdataframe

## Elements of the spatial dataframe
* http://geopandas.org/data_structures.html


## GeoPandas

### Creating spatial dataframes
#### 1. From CSV files
#### 2. From JSON files
#### 3. From Shapefiles

### Analysis with spatial dataframes
### 