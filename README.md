# Home_Sales Analysis with PySpark

## Overview
This project utilizes PySpark SQL to analyze home sales data. The primary goal is to extract key metrics from a dataset, perform SQL queries, and optimize data handling using caching and partitioning techniques.

## Files
- `Home_Sales.ipynb`: Jupyter Notebook containing the PySpark code and analysis.
- `home_sales_revised.csv`: Dataset used for the analysis.

## Process:
1. **Import Libraries**: Import the necessary PySpark SQL functions for data manipulation and analysis.
2. **Read Data**: Load the `home_sales_revised.csv` data into a Spark DataFrame.
3. **Create Temporary Table**: Create a temporary SQL table named `home_sales` from the DataFrame.
4. **Run SQL Queries**: Execute the following SQL queries:
   - Average price for four-bedroom houses sold by year (rounded to two decimal places).
   - Average price of three-bedroom, three-bathroom homes by year built (rounded to two decimal places).
   - Average price of homes with three bedrooms, three bathrooms, two floors, and ≥ 2,000 sq ft by year built (rounded to two decimal places).
   - Average home price per "view" rating for homes priced ≥ $350,000 (include runtime, rounded to two decimal places).
5. **Caching**:
   - Cache the `home_sales` temporary table.
   - Check if the table is cached.
   - Run the last query again using the cached data and compare runtimes.
6. **Partitioning**:
   - Partition the data by the `date_built` field and save it in Parquet format.
   - Create a temporary table from the Parquet data.
   - Run the last query again and compare runtimes.
7. **Uncache Table**: Uncache the `home_sales` temporary table and verify its uncached status using PySpark.

## Key Metrics
- Average home prices for various configurations based on bedrooms, bathrooms, and other criteria.
- Performance improvements through caching and partitioning.

## Technologies Used
- Python
- PySpark
- Jupyter Notebook
