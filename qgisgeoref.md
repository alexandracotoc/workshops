
# Georeferencing Maps in QGIS


Working with a historical map of New Orleans.

-------

## Tiger Lines from the Census

https://www.census.gov/geo/maps-data/data/tiger-line.html

Select 2016 -> Download -> Web Interface

Select a layer type:   Road  -> Submit

Select State and County

*For us, Justin took the TigerLanes and added a projectoion.
Projected in a web mercator. This is for a web mapping application.
We are going to see  meters below because web mercator is measured in meters.
If we use raw Tigerlines, we will see lat/long when we georefectify below.


## QGIS

Open QGIS.

Go to View -> Toolbars (Uncheck to reduce toolbar.)

Left hand veritcal toolbar is how to add data. Choosed  "Add Vector Data".

Browse -> select .shp files (Type = SHP File)

Plugins -> Manage and Install Plugins. In the search box, type in georeference.. Install Geoferencer GDAL is not already installed.

Raster (top menu) ->  Georeferencer -> Add -> Find your map image . Hit ok!

Let's add street names. Go to Layer Properties -> Lab -> Label with FullName  and reduce name size.

### Georeferencer

Now let's add reference points.

Source X (Lat) and Source Y (Long)

Pick a point on your image (historic map of New Orleans) and then to the street grid.

Settings -> Transformation type -> (make a selection depending on your project) Polynomial 1? Play with this!

Settings -> Transformation type -> Target -> WGS84

Settings -> Transformation type ->  Output Raster

Settings -> Transformation type ->  Generate PDF report 

Settings -> Transformation type -> select load QQGIS map when done

Residaul Pixels - They should be similar numbers. Otherwise, an indicator something might really be off. 

"Save GCP Points as" (on hortizontal toolbar) to keep points! Then can use "Load GCP Points as" to load them back in to adjust/ add/ delet points.

Press the Play button to georectify.

## How are we doing?

Layers Panel - Layer Propoerties -> Transparency |  Can see the two layers after georectifying. 

How does it look? Let's add more points!



####  Basemap

Plugins -> OpenLayers Plugin

Use OpenLayers to add a basemap!




------

## Add Layers

Layer -> Create Layer -> New Shapefile Layer   ... select the right kind of "Type". Name the Layer and Save.

Select the pencil button (aka "toggle editing") and add feature (two buttons over).

Click on the map to create. For example, if creating a polygon, click on the map to make one. Once done, click off the "toggle editing" button in order to save. 




------


Add Layer -> Add Vector Layer ->  pull in .shp files

Now have our wards and parade lines.

Now need to merge shapefiles in QGis.

Vector -> Merge Vector Layers -> Merge Wards  by selecting all.  Click on button with Merged to save.

Merged file -> open Attribute Table ->  Add our data into this. Toggle on editing mode.
New Field ->  Name: Ward_id , whole number. Name the wards. 
New Field ->  Add fields for the population. 
Click Stop Editing to save. 

------

# Carto

Wards in one files. Routes in another file. They need be zipped. 
All data procesing in QGIS.  Visualizations in Carto.

## Datasets
New Dataset  -> Browse and upload your .zip file. 

the_geom - if you double click, you'll see a set of coordinates. 
Can add metadata about the project.
Select Create Map.

## Basemap

## Layers
You'll have the wards, parades, and base map.

## Pop-Up
Gives you a pop-up when someone clicks. 

## Widgets

You can create widgets that will allow users to interact with the map based on your data.
Once you have a widget, you can style it as well by click on the three vertical dots on the top right of the box.

For the parade routes, use Type -> Category. (One approach.)


## Maps - Datasets
Make sure to go to the Map view to see the map you created. 
Don't go to the dataset and create another map. It will make a new one. 




 


