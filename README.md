# Working with Spatially Enabled DataFrames 

## Overview

The spatially enabled dataframe (a.k.a. "*spatial dataframe*", "*sdf*", or "*geodataframe*") is a Pandas dataframe with an additional column containing geometric data - exactly like the familiar feature classes we've been working with in ArcGIS. This set of notebooks explores various techniques for creating, analyzing, and visualizing spatial dataframes. In doing so, we delve into the components of geometric data in a dataframe (geometries, geoseries, and projections) as well as the various Python packages that are involved with working with these datasets, mainly *GeoPandas* and the *ArcGIS Python API*, but also the modules on which these packages are dependent: *Shapely*, *Fiona*, *PyProj*, *PyEPSG*, *GeoPy* and *MatPlotLib*. 



## Resources
* http://geopandas.org/index.html
* https://developers.arcgis.com/python/guide/introduction-to-the-spatially-enabled-dataframe/
* https://esri.github.io/arcgis-python-api/apidoc/html/arcgis.features.toc.html#spatialdataframe



## Exercises

### 1. Creating spatial dataframes from CSV file

* Geopandas: `1a-CSV-to-GeoDataFrame-GeoPandas`
* ArcGIS Python API: `1b-CSV-to-SpatialDataFrame-ArcGIS-API`

### 2. Creating spatial dataframes from other file types

* JSON and GeoJSON: `2a-JSON-to-SpatialDataFrame`
* Shapefiles: `2b-Shapefiles-to-SpatialDataframe`

### 3. Spatial analysis & visualization using spatial dataframes

* GeoPandas: `3a-Spatial-analysis-with-Geopandas.ipynb`
* Advanced Analysis: `3b-Advanced-GeoPandas.ipynb`



---

