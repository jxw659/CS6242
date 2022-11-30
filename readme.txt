# Software Requirements
## Python 3.7 or greater
### Python Packages
* pandas v. 1.4.2
* pyproj v 3.4.0
* jupyter v 4.8.1
* requests v 2.28.1
## R 3.6.1
### R Packages
* tidyverse v 1.2.1 ---data wrangling 
* lubridate v 1.7.4 ---date wrangling 
* readr v 1.3.1 ---read csv files 
* caret v 6.0-84 ---one-hot encoding, train/test
* randomForest v 4.6-14 ---rf algorithm
## QGIS v 3.28.1 (https://www.qgis.org/en/site/)
## Tabuleau v 2022.3
# Shape Files
All shape files used by our group can be found in their appropriate GeoData folder. This information is normally found in one of two ways.
1. The city itself might publish information related to its city boarders their own GIS system. (https://geodata-frisco.hub.arcgis.com/datasets/frisco::citylimits/explore)
2. The U.S. Census Bureau publishes shape files that can be used in QGIS to isolate the appropriate polygon. (https://www.census.gov/geographies/mapping-files/time-series/geo/carto-boundary-file.html)
# QGIS
QGIS is used to read in the shapefile as a vector file and then is used to create a grid overlay using this method (https://gis.stackexchange.com/questions/29926/creating-regularly-spaced-defined-of-points-within-polygon-in-qgis)
This data is then exported for use in the Yelp notebook
# Yelp API pull
Inital_Yelp_Data_Pull.ipynb - Is the notebook that we use to transform geographic points into the Yelp restaurant data. The notebook is well documented and should be self explanatory.

# Samuel
We used the "clean_yelp.ipynb" notebook to clean the data.
In the notebook, we used the libraries "pandas", "numpy", "json", and "ast" in a Python environment. We took the raw outputs and concatenated them together and then dropped the duplicated rows based on restaurant IDs. We then extracted the first category of each restaurant as we determined that would be the restaurant's main category for the column "Restaurant Type 1". We determined if pickup, delivery, or reservations were available according the data and created new columns ("Pickup Available", "Delivery Available", and "Reservation Available") for those values. We created a new column for price level (called "Price Level"), basing it on the number of dollar signs in each price entry. We found the total number of photos by finding the length of the list in each photos entry and put the values in the column "number of photos". We then found which city and state the restaurants were in based on the provided location data and added them to the columns "City" and "State". The opening and closing times were given in the hours column and we extracted those hours for the "Opening Time" and "Closing Time" columns. Finally, we determined whether or not the restaurant offered a messaging service for potential customers for the "Has Messaging" column. We did not change "is_closed", "is_claimed","review_count", or "rating".
The final dataframe contained the columns "id";"is_closed"; "is_claimed"; "review_count"; "rating"; "Restaurant Category"; "Pickup Available"; "Delivery Available"; "Reservation Available"; "Price Level"; "number of photos"; "City"; "State"; "Opening Time"; "Closing Time"; and “Has Messaging”.
The values in the "id","Restaurant Category","Price Level", "City", and "State" columns were strings. "Pickup Available", "Delivery Available", "Reservation Available", and "Has Messaging" contain either a 1 or a 0 for each row, with 1 signifying "yes" and 0 meaning "no". "is_closed" and "is_claimed" contain boolean values (i.e., True or False). "Opening Time", "Closing Time", "review_count", "rating", and "number of photos" all contain integer values. Note that the hours were given in the 24 hour format, so that 900 should be interpreted as 9 AM and 2100 should be interpreted as 9 PM.

# Model Development - yelp_model.Rmd
This notebook contains the EDA on the output from "clean_yelp.ipynb". This includes imputing nulls, feature engineering, one-hot encoding, train/test split, random search for parameter tuning, and prediction on the dummy dataset. 
