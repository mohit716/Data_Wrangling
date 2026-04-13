# Rewards Customer Data Wrangling

A Python and pandas project focused on cleaning, standardizing, and validating a customer rewards dataset for downstream analysis.

## Project Overview

This project demonstrates a practical data-wrangling workflow on a customer rewards dataset containing demographic, location, points, and activity fields. The goal was to identify data quality issues, clean inconsistent records, standardize values, and prepare a more analytics-ready dataset.

## Tools Used

- Python
- pandas
- Jupyter Notebook

## Dataset Highlights

- Initial dataset size: 7,252 rows
- Final cleaned subset: 153 rows
- Main columns worked on:
  - User ID
  - Birthdate
  - City
  - State
  - Zip
  - Available Points
  - Total Points Earned
  - Points Spent
  - Joined On
  - Last Seen
  - Tags

## What This Project Does

- Loads and inspects the rewards dataset from CSV
- Identifies missing values using `isna()` and summarizes null counts and percentages
- Converts the `Last Seen` column to datetime format
- Fills missing `Last Seen` values using the earliest valid timestamp
- Drops rows with missing values to create a cleaner working sample
- Removes unnecessary columns such as `Tags`
- Standardizes city values by:
  - trimming whitespace
  - fixing capitalization
  - merging inconsistent spellings and formats
- Standardizes state values by converting full names to abbreviations
- Merges state abbreviations with full state names for cleaner reporting
- Normalizes ZIP codes by truncating long ZIP formats to five digits
- Filters out invalid ZIP codes and clearly incorrect city values
- Produces a cleaner final dataset for analysis or reporting

## Key Data Cleaning Steps

### 1. Missing Value Assessment
The project begins by checking for missing values across the dataset and calculating both raw counts and percentages for each column.

### 2. Datetime Cleaning
The `Last Seen` field is converted from text to datetime format so it can be used more reliably in analysis.

### 3. Missing Timestamp Imputation
Missing values in `Last Seen` are filled with the earliest available valid timestamp.

### 4. Row and Column Cleanup
Rows with critical missing values are removed, and unnecessary columns are dropped.

### 5. Text Standardization
City names are cleaned by fixing spacing, title casing, and inconsistent spellings.

### 6. State Normalization
State names and abbreviations are standardized using a mapping dictionary.

### 7. ZIP Code Validation
ZIP codes are normalized to five digits and invalid values are filtered out.

## Resume-Friendly Summary

- Cleaned and standardized a 7.2K-row customer rewards dataset using pandas, including missing-value analysis, datetime conversion, ZIP code normalization, and city/state standardization.
- Built a data-cleaning pipeline to identify null-heavy fields, impute missing timestamps, validate postal codes, and remove inconsistent records to produce a cleaner analytics-ready dataset.
- Improved dataset usability by normalizing categorical location fields and restructuring columns for downstream analysis/reporting.

## Suggested Future Improvements

- Add visualizations showing missing-value distribution before and after cleaning
- Export the final cleaned dataset as a CSV file
- Add validation rules for birthdates and point-related columns
- Document assumptions for dropped or corrected records
- Include summary statistics and business insights from the cleaned data

## How to Run

1. Open the notebook in Jupyter Notebook or JupyterLab
2. Make sure `RewardsData.csv` is in the same folder as the notebook
3. Run the notebook cells in order

## Outcome

The final result is a cleaner and more standardized version of the rewards dataset that is better suited for reporting, analytics, and downstream data processing workflows.
