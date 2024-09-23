# Sales Performance Dashboard in Power BI

## Project Overview

This project is a **Sales Performance Dashboard** built in **Power BI** to visualize sales data for an online retail store. The dashboard offers insights into key metrics such as total sales, sales by month, sales by product, and sales by country. The data used in this dashboard is based on the **Online Retail Dataset** from the **UCI Machine Learning Repository**.

## Dataset Information

- **Source:** [UCI Machine Learning Repository - Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Retail)
- **Description:** The dataset contains transactional data for a UK-based online retail store from December 2010 to December 2011. It includes fields such as:
  - Invoice number
  - Stock code (Product code)
  - Product description
  - Quantity
  - Invoice date
  - Unit price
  - Customer ID
  - Country

- **Data Cleaning:**
  - Handled missing values, particularly for `CustomerID`.
  - Removed duplicates and performed other standard cleaning procedures.
  - Added a `TotalAmount` column calculated by multiplying `UnitPrice` by `Quantity`.

## Process & Steps

### 1. Data Loading
- Imported the cleaned dataset (`online_retail_cleaned.csv`) into Power BI.
- Loaded dimension tables:
  - `dim_customer` (Customer details)
  - `dim_product` (Product information)
  - `dim_date` (Date dimension for time-based analysis)

### 2. Data Modeling
- Established relationships between fact (`online_retail_cleaned`) and dimension tables (`dim_customer`, `dim_product`, and `dim_date`).
  - **CustomerID**: Linked `dim_customer` and `online_retail_cleaned`.
  - **StockCode**: Linked `dim_product` and `online_retail_cleaned`.
  - **InvoiceDate**: Linked `dim_date` and `online_retail_cleaned`.

### 3. Dashboard Visualizations

1. **Total Sales Overview:**
   - Visualized total sales (`TotalAmount`) and total quantity sold.
   
2. **Sales by Month:**
   - Line chart displaying the trend of total sales over months.
   
3. **Sales by Product:**
   - Bar chart showing the total sales of top products.
   
4. **Sales by Country:**
   - Map visualization displaying total sales by different countries, providing geographic insights.

### 4. Calculations
- **TotalAmount**: A calculated column in the fact table (`online_retail_cleaned`), defined as:
  ```DAX
  TotalAmount = Quantity * UnitPrice

Future Enhancements
Add Forecasting:

Integrate forecasting models to predict future sales based on historical trends.
Advanced KPIs:

Introduce more KPIs (e.g., customer retention, average order value) to expand the analytical depth of the dashboard.
Real-Time Data:

Connect the dashboard to a live data source for real-time sales tracking.
Acknowledgements
Dataset: Thanks to the UCI Machine Learning Repository for providing the dataset used in this project.