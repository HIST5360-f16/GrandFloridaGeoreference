# Florida in QGIS: Geo-referencing Historical Maps
[originally used Monday, April 4, 2016, adapted Friday, September 16, 2016.]
### This tutorial is designed so you can practice the skills you learned in  the [Programming Historian QGIS Tutorial “Geo-referencing in QGIS”]( http://programminghistorian.org/lessons/georeferencing-qgis "Links to Programming Historian")

1. Open a new project; set the CRS by typing 3086 in the filter box and choosing “NAD83 / Florida GDL Albers”

![CRS Selection](/Screenshots/CRS.png)

2. Make sure you have the Georeferencing plug-in installed by clicking on "Plugins" and then "Manage and Install Plugins." Georeferencer GDAL should have a checkmark by it.

3. Now you will set up your modern georeferencing canvas.

   * Add Vector and load cntbnd_sep15.shp [a modern shapefile] to serve as georeferencing canvas.

   * Add Vector: par_citylm_2014.shp

   * For each one – change the “properties” so they are not solid. Turn “labels” on for the city files.

![Canvas](/Screenshots/Canvas.png)

4. Download a PDF of "New Map of Florida, 1860," which is mislabeled, from the Maps ETC website: http://fcit.usf.edu/florida/maps/index.htm

   * Use your image viewer software [ie Microsoft Picture Manager] to convert the JPG file to TIFF. See below for more details.

5. Now you will open the georeferencer. Under "Raster," you will select "Georeferencer." A new window will pop up. It is recommended that you adjust your windows so that you can more easily toggle back and forth between your canvas and the georeferencer.

6. You will now click on the checkered icon on the top left corner of your georeferencing window. This is "open raster." You will then select your TIFF file to upload your historical map. A window will pop up asking you to set the CRS for the TIFF. Set it to NAD83/Florida GDL Albers.

![Raster upload](/Screenshots/Raster upload.png)

7. You will now need to add control points to georeference (sync) your historical map to your canvas. For this exercise, you can use the cities that appear on both maps.

  * Note that for detailed maps like this, it would benefit you to zoom in to the general area of the city you are going to set as a control point on BOTH your georeferencer and your canvas.

8. To set a control point, on your georeferencer window, click on Add Point. Note that the icons may look different depending on your version of QGIS. A window will pop up. Click on "From map canvas." Your georeferencer will minimize and you'll be sent to your canvas. Click once on the corresponding city. You will be sent back to the pop up on your georeferencer. Click OK, and you will have set a control point.

![Add point](/Screenshots/Add point.png)

9. Add six more control points by repeating step 8. Here are some tips on what kinds of points you should select when georeferencing a map like this:

     * Use manmade boundaries, not coastline or rivers which can change

     * Use large cities, ports, or military bases that would have had precise lat/long readings in the 1800s

     * Have at least 3 in the western part of the state

     * Have more than 3 in the eastern part of the state, in heavily populated areas

10. Now you will need to specify transformation settings in your georeferencing window. Click on the "Transformation Settings" button, which should look like a yellow gear. Most everything you can leave as is, but you must make sure the Target SRS is set to your project's CRS: NAD83 / Florida GDL Albers. Then click on Output Raster to select a file to export your georeferenced map to.

![Transformation settings](/Screenshots/Transformation settings.png)

11. Once you've set your Transformation Settings, click on the Play button at the top of your georeferencing window.

12. Once the processing is complete, you can close your georeferencing window. Your modified, georeferenced TIFF will have saved where you assigned it in Transformation Settings. You will also notice that your georeferenced historical map now appears on your canvas. Open the properties for the map and make sure that the CRS is set the same as your canvas. If it is not, your historical map will not appear over your canvas vectors.

13. Compare your georeferenced map to your modern shapefile. You can adjust the transparency of the map on your settings to get a better look at how well they correspond. You may also want to turn off the city labels on your city shp file.

![Complete](/Screenshots/Complete.png)

14. If you want to, you can now use your historical map to identify geographic features and add them to your shp file.

# Data sources for this tutorial
1. Basemaps: http://www.fgdl.org/metadataexplorer/explorer.jsp -- search for "FLORIDA COUNTY BOUNDARIES - SEPTEMBER 2015" and "CITY LIMITS - DERIVED FROM FLORIDA PARCEL DATA - 2014"
2. Historic maps: Florida Maps ETC: http://fcit.usf.edu/florida/maps/index.htm
# How to Convert map-image files
- From JPG to TIFF: Most image viewers will do this. For PC, use  www.irfanview.com [pc] or Microsoft Picture Manager. Mac users, however, can simply Save As or Export in their image viewer and toggle to TIFF.
- From SID to TIFF; irfanview can do this; search the web for other utilities
