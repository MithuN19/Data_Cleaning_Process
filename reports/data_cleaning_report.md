Data Cleaning Report: Melbourne Housing Dataset
Executive Summary
The Melbourne Housing dataset from Kaggle contains property sales records in Melbourne, Australia. The dataset includes various property details such as price, type, location, and physical attributes. The primary goal of this data cleaning process was to prepare the dataset for analysis and visualization by addressing missing values, removing irrelevant features, treating outliers, fixing inconsistencies, and ensuring valid data types.

Key Actions Taken:
Removed records with missing Price

Imputed missing values in BuildingArea, YearBuilt, and CouncilArea

Converted Date column to proper datetime format

Removed irrelevant columns (Address, SellerG, Postcode)

Treated outliers in Price using IQR method

Ensured valid property types and numeric values

Data Quality Assessment
Original Dataset Characteristics:
Rows: ~13,580

Columns: 21

Types: Mixed (categorical, numerical, datetime)

Identified Issues:
Missing Values:

Price contained null values

BuildingArea, YearBuilt, and CouncilArea had substantial missing values

Irrelevant Columns:

Address, SellerG, and Postcode not required for analysis

Outliers:

Extremely high Price values (likely erroneous or luxury properties) skewed the distribution

Inconsistencies:

Some categorical values (Type) needed validation

Date Formatting Issues:

Date was stored as text and required conversion to datetime

Cleaning Methodology
Missing Value Handling:
Dropped rows where Price was missing (essential target column)

Imputed missing BuildingArea and YearBuilt using median values

Filled missing CouncilArea with the mode

Irrelevant Columns:
Removed Address, SellerG, and Postcode to simplify the dataset

Outlier Detection & Treatment:
Applied the IQR method to Price, removing records above the 99th percentile

Inconsistency Fixes:
Verified that Type contained only valid values (h for house, u for unit, t for townhouse)

Converted Date column to datetime format

Feature Engineering:
Created property_age feature by subtracting YearBuilt from the year of sale

Derived land_price_ratio (Price ÷ Landsize) to better understand price distribution

Data Validation:
Ensured all numeric fields (Rooms, Price, BuildingArea) were positive

Confirmed all Date values were within a valid range

Verified categorical consistency for Type and CouncilArea

Results and Impact
Metric	Before Cleaning	After Cleaning
Rows	~13,580	~12,450
Columns	21	18
Missing Values	1,500+	0
Outliers Removed	~200+	0 remaining
Irrelevant Columns	3 removed	-

The cleaned dataset is now consistent, contains no missing values in critical fields, and is optimized for visualization and modeling.

Recommendations
Improve Data Collection: Ensure Price, BuildingArea, and YearBuilt are recorded at the source to reduce missing data

Handle Outliers Dynamically: Consider using domain knowledge thresholds instead of purely statistical methods

Automate Cleaning Pipeline: Build a reusable Python script for cleaning future datasets

Explore Feature Engineering: Additional location-based features (distance to CBD, schools, etc.) could improve insights