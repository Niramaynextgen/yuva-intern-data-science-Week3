# yuva-intern-data-science-Week3

## Project Overview

This week focuses on developing a data cleaning and preprocessing pipeline for the **Customer Churn and Repeat-Purchase Prediction in Beauty & Wellness** project. The pipeline uses the Online Retail II dataset, specifically the `Year 2009-2010.csv` file, to prepare transaction data for further analysis and machine learning.

## Objectives

- Load and inspect the raw retail transaction dataset.
- Standardize column names and data formats.
- Identify and remove exact duplicate records.
- Handle missing values and invalid transaction records.
- Identify cancellations, returns, negative quantities, and unusual prices.
- Detect outliers using the Interquartile Range (IQR) method.
- Generate customer-level features for repeat-purchase and churn prediction.
- Produce data quality reports and visualizations.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- pathlib
- JSON and Python logging

## Dataset

**Dataset:** Online Retail II — `Year 2009-2010.csv`

The dataset contains retail transaction information, including invoice numbers, product codes, product descriptions, quantities, transaction dates, prices, customer IDs, and countries.

## Pipeline Workflow

1. Load the raw dataset.
2. Standardize column names.
3. Generate the initial data quality profile.
4. Remove exact duplicate rows.
5. Convert dates and numeric columns to appropriate data types.
6. Flag missing values, cancellations, returns, invalid prices, and outliers.
7. Separate records with invalid required fields into a quarantine file.
8. Generate customer-level features and illustrative target labels.
9. Export cleaned data, quality reports, and visualizations.

## Output Files

- `cleaned_transactions.csv` — cleaned transaction records.
- `quarantined_records.csv` — records excluded due to specified data-quality issues.
- `customer_features.csv` — customer-level features and target labels.
- `data_quality_profile.csv` — missing-value and data-type summaries.
- `cleaning_summary.json` — summary of cleaning operations.
- `missing_values.png` — missing-value visualization, when applicable.
- `quantity_distribution.png` — quantity distribution.
- `unit_price_distribution.png` — unit-price distribution.
- `line_value_distribution.png` — transaction line-value distribution.
- `cleaning.log` — execution log.

## How to Run

1. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn openpyxl
   ```

2. Place the dataset at the path configured in `INPUT_FILE`.

3. Update `INPUT_FILE` to match the dataset location and filename.

4. Run the Python script:

   ```bash
   python week3_data_cleaning.py
   ```

5. Review the generated files in the `data/processed` and `reports` directories.

## Important Notes

Outliers are flagged rather than automatically deleted. Missing customer IDs are retained in transaction-level data but cannot be used for customer-level supervised modeling. The 30-day future outcome window is illustrative and should be validated before model development.

## Week 3 Outcome

A reproducible preprocessing pipeline that improves data consistency, documents data-quality issues, and prepares transaction and customer-level datasets for subsequent exploratory data analysis and predictive modeling.