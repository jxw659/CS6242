# Software Requirements
## Python 3.7 or greater
### Python Packages
* pandas v. 1.4.2
* pyproj v 3.4.0
* jupyter v 4.8.1
* requests v 2.28.1
## R 
### R Packages
## QGIS v 3.28.1 (https://www.qgis.org/en/site/)
## Tabuleau
# Shape Files
All shape files used by our group can be found in their appropriate GeoData folder. This information is normally found in one of two ways.
1. The city itself might publish information related to its city boarders their own GIS system. (https://geodata-frisco.hub.arcgis.com/datasets/frisco::citylimits/explore)
2. The U.S. Census Bureau publishes shape files that can be used in QGIS to isolate the appropriate polygon. (https://www.census.gov/geographies/mapping-files/time-series/geo/carto-boundary-file.html)
# QGIS
QGIS is used to read in the shapefile as a vector file and then is used to create a grid overlay using this method (https://gis.stackexchange.com/questions/29926/creating-regularly-spaced-defined-of-points-within-polygon-in-qgis)
This data is then exported for use in the Yelp notebook
# Yelp API pull
Inital_Yelp_Data_Pull.ipynb - Is the notebook that we use to transform geographic points into the Yelp restaurant data. The notebook is well documented and should be self explanatory.
# An
# Sam
