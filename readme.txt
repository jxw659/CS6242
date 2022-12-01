# Software Requirements
## Python 3.7 or greater
### Python Packages
* pandas v. 1.4.2
* pyproj v 3.4.0
* jupyter v 4.8.1
* requests v 2.28.1
* ast v 3.7 or greater
* itertools v 3.7 or greater
* numpy v 1.20.1
* json v 2.0.9
## R 3.6.1
### R Packages
* tidyverse v 1.2.1
* lubridate v 1.7.4
* readr v 1.3.1 
* caret v 6.0-84 
* randomForest v 4.6-14 
## QGIS v 3.28.1 (https://www.qgis.org/en/site/)
## Tableau v 2022.3
# Shape Files
All shape files used by our group can be found in their appropriate GeoData folder. This information is normally found in one of two ways.
1. The city itself might publish information related to its city boarders their own GIS system. (https://geodata-frisco.hub.arcgis.com/datasets/frisco::citylimits/explore)
2. The U.S. Census Bureau publishes shape files that can be used in QGIS to isolate the appropriate polygon. (https://www.census.gov/geographies/mapping-files/time-series/geo/carto-boundary-file.html)
# QGIS
QGIS is used to read in the shapefile as a vector file and then is used to create a grid overlay using this method (https://gis.stackexchange.com/questions/29926/creating-regularly-spaced-defined-of-points-within-polygon-in-qgis)
This data is then exported for use in the Yelp notebook

## Guide to Notebooks
### Yelp API pull - Initial_Yelp_Data_Pull.ipynb
To submit a Yelp API request, you need to first sign up for a Yelp account at https://fusion.yelp.com/. Once you have an account, select "Manage API Access" which will reveal your API key. Copy this API key and replace in the notebook Initial_Yelp_Data_Pull.ipynb to start the data pull. This notebook is used to transform geographic points into the Yelp restaurant data. The notebook is well documented and should be self explanatory.
### Clean Data - clean_yelp.ipynb
This notebook is used to clean the data, combine the datasets, drop duplicates, and extract features.
### Model Development - yelp_model.Rmd
This notebook contains the EDA on the output from "clean_yelp.ipynb". This includes imputing nulls, feature engineering, one-hot encoding, train/test split, random search for parameter tuning, and prediction on the dummy dataset. 
### Dummy Data Prediction - Dummy_Data_Creator.ipynb
This notebook creates a dataframe of dummy data that mirrors the train dataset. It generates all possible values given a set of features. The output is fed back to yelp_model.Rmd to predict the classification probabilities. The prediction output is used in the Tableau dashboard, where users can select different feature values to view changes to the prediction probability. 

## Important links
### Git repository - https://github.com/jxw659/CS6242
### Tableau dashboard - https://public.tableau.com/app/profile/an.nguyen7718/viz/YelpRestaurantDashboardTeam149/YelpRestaurantRating

