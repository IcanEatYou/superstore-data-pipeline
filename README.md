# Superstore Data Pipeline | PySpark & Databricks

## Project Overview

This project uses PySpark and Databricks to build a data pipeline for Superstore sales data. I followed the Medallion Architecture to organize the data into Bronze, Silver and Gold layers.

## Architecture

- **Bronze:** Ingested the raw CSV data and stored it as a Delta table.
- **Silver:** Standardized column names, converted data types, validated records and separated rejected rows.
- **Gold:** Created the final cleaned dataset with additional fields for sales analysis.

## Data Quality Checks

- Checked required fields for NULL values.
- Validated sales and quantity values.
- Checked shipping dates against order dates.
- Identified and separated invalid records.
- Tested deduplication using order and product identifiers, then used `row_id` to preserve valid line items.

## Key Results

| Metric | Records |
|---|---:|
| Original records | 9,994 |
| Valid Silver records | 9,694 |
| Rejected records | 300 |
| Final Gold records | 9,694 |

## Technologies Used

- Python
- PySpark
- Databricks
- Delta Lake
- SQL

## Repository Contents

- `superstore_data_pipeline.ipynb` – Complete notebook containing the pipeline implementation and data quality checks.

## How to Run

1. Open the notebook in Databricks.
2. Configure the source CSV path and catalog/schema settings for your workspace.
3. Run the notebook cells in order.

**Note:** The notebook uses a Databricks Volume path. You will need to configure your own source file location before running it.
