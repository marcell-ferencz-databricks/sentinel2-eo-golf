# Raster acquisition, processing and analysis with Databricks

Today we'll answer the biggest open question in the field of Earth observation and GIS systems: __which British golf course has the greenest, healthiest vegetation?__

![john-daly](assets/John-Daly-4.jpg)

In this notebook series, we will demonstrate how to:
- Create and configure a Databricks cluster ready for raster processing, including installing the Databricks Labs Mosaic[↗︎](https://github.com/databrickslabs/mosaic) project and its GDAL[↗︎](https://gdal.org/) extensions;
- Read a publicly available vector dataset describing green space locations in Great Britain and prepare this for later use by reprojecting coordinates and converting the geometries into GeoJSON format;
- Query the Microsoft Planetary Computer's Sentinel 2 catalog[↗︎](https://planetarycomputer.microsoft.com/dataset/sentinel-2-l2a) to obtain links to the relevant imagery for our areas of interest;
- Download the single-band GeoTIFF images to a location in the Databricks file system;
- Read the freshly downloaded imagery into a Spark Dataframe with Mosaic, reproject each raster and collate them into multiband files;
- Join this imagery dataset to the areas of interest and use the AoI geometries to clip the rasters, retaining only the pixels that fall inside each AoI; and
- Use Mosaic's map algebra functions [↗︎](https://databrickslabs.github.io/mosaic/api/raster-functions.html) to compute the pixel-level Normalized Difference Vegetation Index (NDVI) and aggregate this to a single result per AoI.

Start by executing the code in the `SETUP` notebook, then begin running through the series of notebooks:
- `00 Acquire data` - Acquire and store vector and raster datasets
- `01 Process imagery` - Reshape and clip the rasters
- `02 Analyse results` - Run map algebra functions over the resulting sub-rasters to produce AoI-level results.
