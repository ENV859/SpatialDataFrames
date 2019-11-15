# Working with Spatially Enabled DataFrames 

## Overview

The spatially enabled dataframe (a.k.a. "*spatial dataframe*", "*sdf*", or "*geodataframe*") is a Pandas dataframe with an additional column containing geometric data - exactly like the familiar feature classes we've been working with in ArcGIS. This set of notebooks explores various techniques for creating, analyzing, and visualizing spatial dataframes. In doing so, we delve into the components of geometric data in a dataframe (geometries, geoseries, and projections) as well as the various Python packages that are involved with working with these datasets, mainly *GeoPandas* and the *ArcGIS Python API*, but also the modules on which these packages are dependent: *Shapely*, *Fiona*, *PyProj*, *PyEPSG*, *GeoPy* and *MatPlotLib*. 



## Resources
* http://geopandas.org/index.html
* https://developers.arcgis.com/python/guide/introduction-to-the-spatially-enabled-dataframe/
* https://esri.github.io/arcgis-python-api/apidoc/html/arcgis.features.toc.html#spatialdataframe



## Exercises

### 1. Creating spatial dataframes using GeoPandas and the ArcGIS Python API:  

* From CSV files: `01-CSV-to-SpatialDataFrame.ipnyb`
* From FeatureClasses: `02-FeatureClass-to-SpatialDataFrame.ipynb`

### 2. Spatial analysis using spatial dataframes

* Beginners: `3-Spatial-analysis-with-GeoDataframes.ipynb`
* Advanced: `4-Advanced-GeoPandas.ipynb`

### 3. Data visualization with dataframes and spatial dataframes

* Plots and graphs with Pandas
* Plots and graphs with MatPlotlib
* Plots and graphs with Plotnine (ggplot)
* Making maps with Geopandas
* Making maps with the ArcGIS Python API



---

