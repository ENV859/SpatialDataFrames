# Working with Spatially Enabled DataFrames 

### Geopandas, Shapely, and Fiona (and GDAL)

A few notes before we dive in. First on popular packages and nomenclature. A package called [**GeoPandas**](https://geopandas.org/) is the open source standard for working with spatial dataframes. Geopandas enables your Pandas dataframes to have a column of **geometries** (points, lines, polygons, as well as multi-points, polylines, and multi-polygons) in addition to the standard numeric and text based column types standard to Pandas. These columns of geometries are called **GeoSeries**, and dataframes that have these GeoPandas GeoSeries are called **GeoDataframes**. 

When installed in your Python environment, GeoPandas also installs a number of other packages on which it is dependent (a.k.a. *dependencies*). The ones to note include <u>Shapely</u> and <u>Fiona</u>. The [**Shapely**](https://shapely.readthedocs.io/en/latest/) package allows us to work with geometric features, much like those we worked with using ArcPy, but with Shapely, we are free from needing any ESRI license! (Instead Shapely uses the open source [GDAL](https://gdal.org/) engine). In addition to adding geometric objects to our coding environment, Shapely also provides functions for doing analyses with these objects! The [**Fiona**](https://fiona.readthedocs.io/en/latest/) package allows us to read and right various GIS file types in Python, enabling us to work with existing files and facilitates going back and forth between Python and traditional GIS software like ArcGIS Pro. 

### ArcGIS API for Python

We'll deal with Geopandas, Shapely and Fiona in the Jupyter Notebooks we are about to access. However, ESRI is also embracing the open source world with its [**ArcGIS API for Python**](https://developers.arcgis.com/python/). It has many similarities to GeoPandas and also does not require any ESRI license for its basic functionality. In a sense, the ArcGIS Python API serves as a bridge between ArcGIS Online and Python, but it also includes a number of useful widgets for mapping and analyzing data. 

There is much more to the ArcGIS Python API than we'll discuss here. Instead, we'll focus on the API's "**Spatially Enabled Dataframe**", i.e., its version of GeoPandas' Geo Dataframe.  You'll see that the two have many similarities and concepts learned from one fairly easily translate to the other. 

### Structure of our lessons

As before, we'll learn by doing. I've constructed a number of Jupyter Notebooks that explore the basic concepts of both GeoPandas geodataframe and ArcGIS's spatially enabled dataframes, which I interchangeably call spatial dataframes. Below is a listing of the key learning objectives associated with each notebook. 

Prior to running these notebooks, however, we'll have create a new Conda environment and install the necessary packages. Instructions for that follow.



## Resources
* http://geopandas.org/index.html
* https://developers.arcgis.com/python/guide/introduction-to-the-spatially-enabled-dataframe/
* https://esri.github.io/arcgis-python-api/apidoc/html/arcgis.features.toc.html#spatialdataframe



| Notebook                      | Learning Objectives                                          |
| ----------------------------- | ------------------------------------------------------------ |
| 1. CSV to SDF                 | **GeoPandas & GeoDataFrames<br />• Create, edit, & describe properties of **geometric objects** using **Shapely**<br />• Create a **GeoSeries** from a list of coordinate pairs<br/>• Convert a dataframe with coordinate fields into a **GeoDataframe**<br />• Look up and use WKIDs to define coordinate reference systems in geodataframes<br />• Explore properties of geodataframes<br />• Make simple plots of spatial features in geodataframes<br />**ArcGIS Python API & Spatially Enabled Dataframes**<br />• Convert dataframes with coordinate fields into a Spatial Dataframe<br />• Explore properties of spatial dataframes<br />• Reproject a spatial dataframe<br />• Make simple maps of spatial dataframe features<br />• Translate between spatial dataframes and geodataframes |
| 2a. Feature Class to GDF      | • Importing **shapefiles into geodataframes** using GeoPandas<br />• Creating **choropleth maps** from geodataframes<br />• Importing **GeoJSON files into geodataframes** using GeoPandas |
| 2b. Feature Class to SDF      | • Importing **shapefiles into spatial dataframes** using the ArcGIS Python API<br />• Quick maps with **spatial dataframes**<br />• Importing **AGOL feature services into spatial dataframes** |
| 3. Spatial analysis with SDFs | • Execute the "**data science workflow**" with a GeoPandas<br />  - **Read data** into a geodataframe (CSV and GeoJSON)<br />  - **Explore the data**: columns/column types, summaries, plots<br />  - **Analyze** the data...<br />  - **Visualize** results<br />• **Subset features** in a geodataframe by **attribute**<br />• **Merge geodataframes**<br />• **Dissolve geodataframe features** based on an attribute value<br />• **Join attributes** to a geodataframe<br />• **Spatially join** data from one geodataframe to another<br />• Generate various **plots** from single and multiple geodataframes<br />• **Saving a geodataframe** to a feature class |

---

