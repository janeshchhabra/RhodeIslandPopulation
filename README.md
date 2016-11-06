# Rhode Island Population Visualization
This project is a geospatial mapping of Rhode Island populations. It is based on Census Tract data. In order to create the topojson file used for this project, I downloaded Rhode Island Census tract shp files, Rhode Island Census tract population csv, US County shp files, and US state shp files. I did the following to create the file:

* Use QGIS on the county shp files to isolate Rhode Island and save that as a new shp file
* Use QGIS on the state shp files to isolate Rhode Island and save that as a new shp file
* Once that is done, edit the csv to change GEO.id2 to just GEO
* Run the following command: 
```
topojson -o STATE.json -e ACS_14_5YR_B01003_with_ann.csv --id-property=+GEO,+GEOID -p population=+HD01_VD01,area=+ALAND -s 1 --cartesian --width 650 --margin 20 -- COUNTY.shp census_tracts.shp STATE.shp
```
Note: you may have to change the width and margin. Also, if the resolutions of the shp files are different, there may be some issues in the display if the state is bumpy and not smooth. 

  
