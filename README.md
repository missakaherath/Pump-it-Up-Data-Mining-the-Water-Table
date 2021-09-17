# Pump-it-Up-Data-Mining-the-Water-Table

Repository: https://github.com/missakaherath/Pump-it-Up-Data-Mining-the-Water-Table.git

Notebook: https://colab.research.google.com/drive/1IwxOV-lKUlGDVbIr5SuHnGzIdSs-r5wb#scrollTo=Eb6uQV-VS9vX

Used models: RandomForest, XGBoost

Competition Link: https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/

##

* Columns funder, installer, subvillage, public_meeting, scheme_management, scheme_name and permit were contained missing values. those were filled using a constant value 'Unknown'.

* There weren't any misssing values in the columns with numerical values.

* Though there are 1897 'funder' categories, most of the rows contain a small subset of those funders (Majority of wells were funded by a small set of funders). therefore rows with top 5 values of the 'funder' categories were kept and others marked as 'other'.
This helps to reduce the amount of dummy columns while maintaining the information contained in the column.

* The same approach was applied to 'installer', 'scheme_management' and 'construction_year' columns.

* Since there are a lot of unique values and top valued columns don't cover a majority of them, 'subvillage', 'scheme_name', 'wpt_name' columns were dropped.

* Data in the columns with categorical, string valued data were converted to lower case to keep consistency in data.

* 'date_recorded' column was changed to represent the number of days ('days_since_recorded') since the most recently recorded datetime, as more recently recorded pumps might be more likely to be functional.

* Since basin, lga, ward and region contain geographical information which is unlikely to be useful to the model, they will be removed

* extraction_type, extraction_type_group and extraction_type_class contains similar information. therefore 'extraction_type', 'extraction_type_group' columns were removed.

* 'management' and 'management_group' columns are almost identical to 'scheme_management'. threfore they were removed.

* Since payment and payment_type contain identical data, payment column were dropped.

* 'quality_group' column was dropped since water_quality and quality_group contain identical data.

* 'quantity_group' column was dropped since Quantity and quantity_group contain identical data.

* 'source' column was dropped since Source and source_type contain very similar information.

* 'num_private' was removed since, hasn't been given a discription, is seems to be unnecessary.

* gps_height, longitude, latitude, region_code and district_code are all geographic info. therefore these columns will be removed and only gps_height column will be kept.

* 'recorded_by' column had same value in all the rows. therefore it was dropped.

* construction_year column was converted to a column with categorical data.

* Standard normalization was applied to 'gps_height', 'amount_tsh' and 'population' columns.

* String valued columns were encoded using one hot encoding.

## Used Models

* RandomForestClassifier
* XGBClassifier

## Submission 

![Capture](https://user-images.githubusercontent.com/47146603/133830757-46f6cf0b-d40f-4ca4-8340-8378873a9d87.PNG)
