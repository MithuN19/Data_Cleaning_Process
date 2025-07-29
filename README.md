# Data_Cleaning_process
# Melbourne Housing - Data Cleaning Project

## Project Overview

This project is focused on cleaning the **Melbourne Housing Dataset** from Kaggle, which contains property sales data across Melbourne, Australia.  
The dataset includes information on property type, price, size, location, and sale dates with **13,580 rows and 21 columns** in its original form.

The goal of this project was to transform the raw dataset into an analysis-ready format by:
- Identifying and handling missing values
- Removing irrelevant and duplicate records
- Detecting and treating outliers
- Correcting data inconsistencies and invalid values
- Validating data integrity
- Documenting the cleaning process

---

## Key Tasks Performed

### Missing Value Handling
- Filled or removed missing values in:
  - `Price`: Dropped rows with missing values
  - `BuildingArea` and `YearBuilt`: Replaced with median values
  - `CouncilArea`: Filled with mode (most frequent value)

### Duplicate & Outlier Removal
- Removed duplicate records
- Treated outliers in:
  - `Price` using IQR method (removed extreme values above 99th percentile)

### Inconsistency Fixes
- Converted `Date` column to proper datetime format
- Verified valid property types: `h` (house), `u` (unit), `t` (townhouse)
- Removed irrelevant columns: `Address`, `SellerG`, `Postcode`

### Feature Engineering
- `property_age` = year of sale - `YearBuilt`
- `land_price_ratio` = `Price` ÷ `Landsize`

### Validation
- Ensured all numeric fields (`Rooms`, `Price`, `BuildingArea`) had valid positive values
- Checked that all dates fell within valid ranges
- Verified categorical data consistency for `Type` and `CouncilArea`

---

## Dataset Source

> [Melbourne Housing Snapshot Dataset on Kaggle](https://www.kaggle.com/datasets/dansbecker/melbourne-housing-snapshot)

---

## How to Run

1. Open `data_cleaning_process.ipynb` in Jupyter Notebook or Google Colab.
2. Run all cells from top to bottom.
3. The cleaned dataset will be saved and ready for analysis.

---

## Author

- **Student Name:** *W.P.M.H. Wijesinghe*
- **Course:** Intelligent Systems
- **Institution:** *Horizon Campus*
- **Date:** *2025-07-29*

---

## License

This project is developed solely for academic purposes and is not intended for commercial use.
