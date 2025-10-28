# Working with Spatial DataFrames 

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




| **Notebook**                                                 | **Learning Objectives**                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **1a. Creating spatial dataframes<br />&emsp;using Geopandas** | **Geopandas and GeoDataFrames<br />• Contrast a **spatial dataframe** to a typical dataframe<br />• List the two **Python libraries** used for creating and working with spatial dataframes<br />• Create a GeoPandas **GeoDataFrame** from a **CSV file** containing spatial coordinates<br />&emsp;- Construct a **GeoSeries** object from coordinate columns in a Pandas dataframe<br />&emsp;- Lookup the **ESPG code** or **WKID** for a given coordinate reference system<br />&emsp;- Construct a **GeoDataFrame** from a GeoSeries object and an EPSG code/WKID<br />• Explore the **properties** of GeoDataFrames<br />• **Transform** (reproject) a GeoDataFrames<br />• Make simple **plots** of GeoDataFrames<br />• Create a GeoDataFrame from an existing **ShapeFile**<br />• Understand the role the **Fiona** package plays in creating GeoDataFrames from various file formats<br />• Create a GeoDataFrame from a **GeoJSON** file<br />• Create a GeoDataFrame from an existing **KML** |
| **1b. Creating spatial dataframes<br />&nbsp;&emsp;using the ArcGIS API for Python** | **ArcGIS Python API & Spatially Enabled Dataframes**<br />• Convert CSV files with coordinate fields into a Spatial Dataframe<br />• Explore properties of spatial dataframes<br />• Create a Spatial Dataframe from an existing feature class<br />• Create a Spatial Dataframe from a feature layer service<br />• Reproject a Spatial Dataframe<br />• Make simple maps of spatial dataframe features |
| **2. Spatial analysis w/ GeoDataFrames**                     | • Execute the "**data science workflow**" with a GeoPandas<br />  - **Read data** into a geodataframe (CSV and GeoJSON)<br />  - **Explore the data**: columns/column types, summaries, plots<br />  - **Analyze** the data...<br />  - **Visualize** results<br />• **Subset features** in a geodataframe by **attribute**<br />• **Merge geodataframes**<br />• **Dissolve geodataframe features** based on an attribute value<br />• **Join attributes** to a geodataframe<br />• **Spatially join** data from one geodataframe to another<br />• Generate various **plots** from single and multiple geodataframes<br />• **Saving a geodataframe** to a feature class |

## Section Prep

#### 1. Create a new Conda environment ("`gis`") and install necessary packages

This section involves several new Python packages that we'll have to install. As we can't be sure these will conflict with existing packages, we'll create a new Conda environment and install our packages in that environment. We'll call this environment `gis` to maintain consistency with my documentation and files. 

Recall that to create a new environment, we first need to **open your Python Command Prompt**. From there, run the following commands. (You can skip the comment lines, there to explain what each command does...)

```
# Create a fresh environment
conda create --clone arcgispro-py3 --name gis

# Activate the environment
activate gis

# Install geopandas using pip
pip install geopandas

# Install additional packages
conda install fiona
conda install -c conda-forge contextily -y
```

#### 2. Fork and clone the `SpatialDataframes` repository

The notebooks for this section are included in the repository <https://github.com/env859/SpatialDataFrames>. 

* Fork the repository to your own GitHub account
* Clone the forked repository (using Git Bash or GitHub desktop) to your local machine.



#### 3. Create a new Jupyter Notebooks shortcut and run it

The repository has a shortcut to run Jupyter Notebooks using your new environment, but it's good practice to create one yourself. 

* Navigate into your newly cloned repository.

* Create a new text file and rename it "RunJupyter.bat".

* Open the text file in a text editor and add the lines

  ```
  @set the_env=gis
  call "C:\Program Files\ArcGIS\Pro\bin\Python\Scripts\activate.bat" "%the_env%"
  call "%localappdata%\ESRI\conda\envs\%the_env%\scripts\jupyter-notebook.exe" %cd% 
  call "C:\Program Files\ArcGIS\Pro\bin\Python\Scripts\deactivate.bat"
  ```

  > * Line 1 creates a system variable named "the_env", setting its value to "gis" (the name of the Conda environment created earlier). 
  > * Line 2 activates this Conda environment. (Note the use of the variable set in line 1...)
  > * Line 3 executes the command to start Jupyter notebook stored in the Conda environments installation folder.
  > * Line 4 deactivates the Conda environment. This line will run once Jupyter is closed. 

* After this you should be good to go!