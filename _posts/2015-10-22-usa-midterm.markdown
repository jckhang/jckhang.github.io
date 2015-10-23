---
layout: post
title: "Spatial Analytics Midterm Review"
modified:
categories:
excerpt:
tags: [Midterm]
image:
  feature:
date: 2015-10-22T12:30:09-04:00
---

<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. General Concepts</a>
<ul>
<li><a href="#sec-1-1">1.1. Relative path:</a></li>
<li><a href="#sec-1-2">1.2. Attribute Table:</a></li>
<li><a href="#sec-1-3">1.3. Selection of features:</a></li>
<li><a href="#sec-1-4">1.4. Types of Geospatial Data:</a></li>
<li><a href="#sec-1-5">1.5. Types of shapefiles:</a></li>
<li><a href="#sec-1-6">1.6. Metadata:</a></li>
<li><a href="#sec-1-7">1.7. What is GIS:</a></li>
<li><a href="#sec-1-8">1.8. Joining Data:(Table and spatial data):</a></li>
<li><a href="#sec-1-9">1.9. Model Builder:</a></li>
<li><a href="#sec-1-10">1.10. Layer File(.lyr):</a></li>
<li><a href="#sec-1-11">1.11. Types of symbology:</a></li>
<li><a href="#sec-1-12">1.12. Geodatabase:</a></li>
<li><a href="#sec-1-13">1.13. Projection Systems:</a></li>
<li><a href="#sec-1-14">1.14. Definition Query:</a></li>
<li><a href="#sec-1-15">1.15. Choropleth Maps:</a></li>
<li><a href="#sec-1-16">1.16. Normalization:</a></li>
<li><a href="#sec-1-17">1.17. Layer Package:</a></li>
<li><a href="#sec-1-18">1.18. Interactive GIS:</a></li>
<li><a href="#sec-1-19">1.19. Visible Scale Range:</a></li>
<li><a href="#sec-1-20">1.20. Maptip:</a></li>
<li><a href="#sec-1-21">1.21. 2 types of animation(cumulative/non-cumulative):</a></li>
<li><a href="#sec-1-22">1.22. Geoprocessing:</a></li>
<li><a href="#sec-1-23">1.23. Digitization:</a></li>
<li><a href="#sec-1-24">1.24. Geocoding:</a></li>
<li><a href="#sec-1-25">1.25. Geocoding types:</a></li>
<li><a href="#sec-1-26">1.26. Conceptual Components of geocoding:</a></li>
</ul>
</li>
<li><a href="#sec-2">2. Additional:</a>
<ul>
<li><a href="#sec-2-1">2.1. Components of a good map:</a></li>
<li><a href="#sec-2-2">2.2. Navigation:</a></li>
<li><a href="#sec-2-3">2.3. Bookmark:</a></li>
<li><a href="#sec-2-4">2.4. Set selectable layers:</a></li>
<li><a href="#sec-2-5">2.5. What is a fishnet map</a></li>
<li><a href="#sec-2-6">2.6. What is accumulation of animation means in a map</a></li>
<li><a href="#sec-2-7">2.7. Is there a perfect projection?</a></li>
<li><a href="#sec-2-8">2.8. Scale types of measurement:</a></li>
<li><a href="#sec-2-9">2.9. Types of coordinate system:</a></li>
<li><a href="#sec-2-10">2.10. Scale comparison, which one has a larger scale, map of the United States or a building?</a></li>
<li><a href="#sec-2-11">2.11. What's the difference between clip and intersect?</a></li>
</ul>
</li>
</ul>
</div>
</div>


# General Concepts<a id="sec-1" name="sec-1"></a>

## Relative path:<a id="sec-1-1" name="sec-1-1"></a>

In Map Document Properties, paths can be absolute or relative. Check the pathnames as store relative pathnames to data sources.

## Attribute Table:<a id="sec-1-2" name="sec-1-2"></a>

Right click a layer in the Table of Contents, open its attribute table.

All you can do to play with Attribute Table:
1.  Select features and Select by Attributes.
2.  Switch selection.
3.  Add Field.
    -   Stop Editing, or you will encounter "error: Cannot add field". Same as most cases.
4.  Drag and move a field.
5.  Sort Ascending/Descending.
6.  Field Calculation.
7.  Export table.

## Selection of features:<a id="sec-1-3" name="sec-1-3"></a>

Ways to select features:

1.  Select by Find: Use Find button on the Tools toolbar and search with feature's names.
2.  Select Features Tool: Use Select Features button on the Tools toolbar and click.
3.  Select by graphic:  Use Select by Rectangle/Polygon/Circle.
4.  Select by attribute: Open attribute table and click the records(rows) or use Select by attribute.

## Types of Geospatial Data:<a id="sec-1-4" name="sec-1-4"></a>

1.  Raster(.JPG, .TIF, .GIF)

Rasters are pictures. They are images that are indexed by their pixels. They are continuous and cannot be divided into smaller units. All raster maps are rectangular.  Each pixel has a coordinate, locating it in the broader raster array. These values are not stored in the cells themselves, but instead are calculated from a benchmark, like the corner of the image, by an algorithm. They are large files.

1.  Vector(points, lines, polygons)

Vector data is data that has a spatial component, or X,Y coordinates assigned to it.

## Types of shapefiles:<a id="sec-1-5" name="sec-1-5"></a>

-   .shp: ESRI file that represents the feature geometry. Each shapefile has it’s own .shp file that can represent points, lines and polygons in a map. Mandatory

-   .shx: ESRI and AutoCAD shape index position. This type of file is used to search forward and backwards. Mandatory.

-   .dbf: Standard database file used to store attribute data and object IDs. .dbf can be opened in Microsoft Access or Excel. Mandatory.

-   .prj: This file type contains the metadata associated with the shapefiles coordinate and projection system. If this file does not exist, the error “unknown coordinate system” will appear. To fix this error, the “define projection” tool generates .prj files. Optional.

-   .xml: This file type contains the metadata associated with the shapefile. Delete this file, and you essentially delete your metadata. This file type (.xml) can be opened and edited in any text editor. Optional.

-   .sbn: Spatial index file that optimizes spatial queries. This file type is saved together with a .sbx file. These two files make up a shape index to speed up spatial queries. Optional.

-   .sbx: Similar to .sbn files, this file type speeds up loading times. It works with .sbn files to optimize spatial queries. We tested .sbn and .sbx extensions and found that there were faster load times when these files existed. It was 6 seconds faster (27.3 sec versus 33.3 sec) comparing with/without .sbn and .sbx files. Optional.

## Metadata:<a id="sec-1-6" name="sec-1-6"></a>

Information that describes items in ArcGIS is called metadata. In an item's metadata you can record whatever information is important for your organization to know about that item. This might include information about how accurate and recent the item is, restrictions associated with using and sharing the item, important processes in its life cycle such as generalizing features, and so on.

## What is GIS:<a id="sec-1-7" name="sec-1-7"></a>

1.  GIS-Geographic Information System.
2.  GIS are computerized systems designed for the storage, retrieval, and analysis of geographically referenced data.
3.  GIS applications are tools that allow users to create interactive queries, analyze spatial information, edit data in maps, and present the results of all these operations.
4.  Geographic information science is the science underlying geographic concepts, applications, and systems.

## Joining Data:(Table and spatial data):<a id="sec-1-8" name="sec-1-8"></a>

Two types of join: join by attributes and spatial join by the features locations

## Model Builder:<a id="sec-1-9" name="sec-1-9"></a>

It enables reproduceable geoprocessing for different maps. It allows user to create their own tools by combining some existing tools and features. The process is able to merge several steps together and reduce work amount.

## Layer File(.lyr):<a id="sec-1-10" name="sec-1-10"></a>

1.  A map layer defines how a GIS dataset is symbolized and labeled (that is, portrayed) in your map views.
2.  A layer can exist outside your map as a layer file (.lyr). This makes it easy for others to access the layers you've built.

## Types of symbology:<a id="sec-1-11" name="sec-1-11"></a>

1.  Features:
    -   Single symbols:
        -   Polygons: As background color.
        -   Points, lines: Most common type of symbology.
2.  Categories:
    -   Unique Values:
        Often used for polygons and points.
3.  Quantities:
    1.  Graduated colors:
    2.  Graduated symbols:
    3.  Proportional symbols:
    4.  Dot Density
4.  Charts:
    1.  Pie
    2.  Bar/Column
    3.  Stacked
5.  Multiple Attributes:

## Geodatabase:<a id="sec-1-12" name="sec-1-12"></a>

1.  The geodatabase is a "container" used to hold a collection of datasets (GIS features, tables, raster images.
2.  Geodatabase elements:
    1.  Table
    2.  Feature Class
        1.  Points(c)
        2.  Lines(c)
        3.  Polygons(c)
        4.  Annotation
        5.  Dimensions
        6.  Multipoints
        7.  Multipatches
    3.  Raster Datasets

## Projection Systems:<a id="sec-1-13" name="sec-1-13"></a>

Metric properties of maps: Area, Shape, Direction, Bearing, Distance, Scale.

Three types of Map Projections:

1.  Plane: **Stereographic**
    -   It is conformal, meaning that it preserves angles.
    -   It is neither isometric nor area-preserving: that is, it preserves neither distances nor the areas of figures.

2.  Cylindrical: **Mercator**
    -   **Conformal projection**
    -   Angles and shapes of small objects preserved
    -   The size/shape/area of large objects distorted
    -   Seldom used for world maps

3.  Conic: **Albers**
    -   **Equivalent projection**
    -   Preserves accurate area
    -   Scale and shape are not preserved

## Definition Query:<a id="sec-1-14" name="sec-1-14"></a>

-   In Layor->Properties->Definition Query
-   Or in Symboloty->Quantities->Classify->Exclusion

## Choropleth Maps:<a id="sec-1-15" name="sec-1-15"></a>

A choropleth map uses color fill in polygons to represent numeric attribute values. Generally darkness of a colorfill represents either increasing or decreasing values.

## Normalization:<a id="sec-1-16" name="sec-1-16"></a>

The process of dividing one numeric attribute value by another to minimize differences in values based on the size of areas or the number of features in each area. For example, normalizing (dividing) total population by total area yields population per unit area, or density.

## Layer Package:<a id="sec-1-17" name="sec-1-17"></a>

A layer can be saved with its data as a layer package (.lpk). A layer package includes both the layer properties and the dataset referenced by the layer. With a layer package, you can save and share everything about the layer—its symbolization, labeling, field properties, and the data.

## Interactive GIS:<a id="sec-1-18" name="sec-1-18"></a>

An interactive map is a map in digital form that allows you to unanipulate the map display and query the map to get information you need using a set of tools provided with the maps.

## Visible Scale Range:<a id="sec-1-19" name="sec-1-19"></a>

-   Out beyond refers to the smallest desired map scale at which the layer is visible in the display (the minimum scale). This will use the larger of the map scale numbers. In beyond refers to the largest desired visible map scale, which is the smaller of the map scale numbers (the maximum scale).
-   Right-click the layer in the table of contents and click Properties (or double-click the layer) to open the Layer Properties dialog box. You can set a layer's visible scale range on the General tab of the Layer Properties dialog box.

## Maptip:<a id="sec-1-20" name="sec-1-20"></a>

Map tip is text box over important features in a map. it is used to highlight certain points and add text explanation in context.

## 2 types of animation(cumulative/non-cumulative):<a id="sec-1-21" name="sec-1-21"></a>

-   Click Layer->Properties->Time, Enable time on this layer.
-   Check Display Data Cumulatively or not.

## Geoprocessing:<a id="sec-1-22" name="sec-1-22"></a>

1.  clip:
    -   “Cookie cutting” of one layer using another layer.
2.  buffer
    -   Rings drawn around features at a specified.
3.  dissolve
    -   This function aggregates (combines) features that have the same value in a field in the attribute table. It is helpful if you want to simplify the number of features in a layer to the unique ones you have.
4.  intersect
    -   Create a new feature class combining all the features and attributes of two inputm overlaying feature classes.
5.  union
    -   Overlays two polygon layers
6.  merge
    -   Combine several adjacent layers into one layer

## Digitization:<a id="sec-1-23" name="sec-1-23"></a>

1.  What is it?
    Digitizing is the process by which coordinates from a map, image, or other sources of data are converted into a digital format in a GIS. This process becomes necessary when available data is gathered in formats that cannot be immediately integrated with other GIS data.
2.  Why is it useful?
    -   New maps
    -   Map features are wrong
    -   Missing features

## Geocoding:<a id="sec-1-24" name="sec-1-24"></a>

Geocoding is the process of converting addresses (like "1600 Amphitheatre Parkway, Mountain View, CA") into geographic coordinates (like latitude 37.423021 and longitude -122.083739), which you can use to place markers on a map, or position the map.

## Geocoding types:<a id="sec-1-25" name="sec-1-25"></a>

-   Geocoding by ZIP code.
-   Geocoding by street address.

## Conceptual Components of geocoding:<a id="sec-1-26" name="sec-1-26"></a>

Address locator, spreadsheet, reference file like street network or zipcode.

# Additional:<a id="sec-2" name="sec-2"></a>

## Components of a good map:<a id="sec-2-1" name="sec-2-1"></a>

1.  Title
2.  Orientation
3.  Source
4.  Scale
5.  Legend
6.  Author
7.  Navigation
8.  Date

## Navigation:<a id="sec-2-2" name="sec-2-2"></a>

Different Navigation Tools:
1.  Zoom in/out: Zoom in by clicking or dragging a box.
2.  Pan: Pan by dragging. Double click to recenter and zoom in. Shift+drag to zoom to rectangle.
3.  Full Extent: By default, zoom to the extent of all the data in the active data frame.
4.  Fixed Zoom In/Out: Zoom in on the center of the map.
5.  Zoom to layer
6.  Zoom to selected feature
7.  Bookmark

## Bookmark:<a id="sec-2-3" name="sec-2-3"></a>

Click Bookmarks > Create Bookmark

## Set selectable layers:<a id="sec-2-4" name="sec-2-4"></a>

The purpose is to simplify the selection processs and avoids selecting multiple features from different layers.

## What is a fishnet map<a id="sec-2-5" name="sec-2-5"></a>

The output will be a set of rectangular polygons, with the option of creating label points for each as well.

## What is accumulation of animation means in a map<a id="sec-2-6" name="sec-2-6"></a>

Accumulation of animation shows one particular event developing progress as the time move along. The events accumulates instead of blinking on the maps at certain time.

## Is there a perfect projection?<a id="sec-2-7" name="sec-2-7"></a>

There is no perfect projections. since the earth has three dimensions and is depicted on a two dimensional map. Some features will be inevitably distorted or disoriented. most of the maps can only maintain equal distance or equal area.

## Scale types of measurement:<a id="sec-2-8" name="sec-2-8"></a>

Norminal: like zipcodes,
Ordinal: A natural ranking of order, like temperature rank
Interval: Quantitative data that is measure on a physical scale that has equal intervals without percentages or ratios.
Ratio: Quantitative data in which ratios between two values have definite meaning.

## Types of coordinate system:<a id="sec-2-9" name="sec-2-9"></a>

Geographic and projected. Geographic coordinate systems use latitude and longitude coordinates for locations while projected coordinate systems use rectangular coordinates.

## Scale comparison, which one has a larger scale, map of the United States or a building?<a id="sec-2-10" name="sec-2-10"></a>

Building has a larger scale.

## What's the difference between clip and intersect?<a id="sec-2-11" name="sec-2-11"></a>

The main difference will be in the attributes of the results. When using Clip only the input feature’s attributes will be in the output (none from the clip feature), where if you used Intersect the attributes form all features used will be in the output.

Happy Midterm.