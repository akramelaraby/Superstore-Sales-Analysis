# Superstore-Sales-Analysis
This project utilizes a combination of SQL, Tableau, and Python to conduct a comprehensive sales analysis for Superstore retail.

Superstore Sales Analysis
Unleashing the Power of Data-Driven Insights

This repository provides a comprehensive analysis of Superstore's sales performance, utilizing SQL, Tableau, and Python. By diving deep into the data, we aim to uncover valuable insights that can drive strategic business decisions.

# Key Objectives:

- Analyze sales trends by region, product category, and customer segment
- Identify top-performing customers and products
- Examine the impact of shipping modes on sales
- Forecast future sales trends


The main objectives are:

To analyze total sales by region, product category, and customer.
To identify top-performing customers and products.
To examine shipping modes and their impact on sales.
To track sales trends over time and seasonal patterns.
Key Insights:
Sales Analysis by Region: Identifies the top regions for sales performance. salesdashboard1
Customer Segmentation: Utilizes RFM (Recency, Frequency, Monetary) analysis to segment customers based on their purchasing behavior. salesdashboard3
Shipping Performance: Analyzes shipping speed and delivery time and its effect on total sales.
Top Products: Identifies the most profitable products and categories. salesdashboard2
Predictive Analytics Overview
Methodology
Data Preparation:
Processed historical sales data to clean, aggregate, and structure it for forecasting.
Modeling:
Used Facebook Prophet to build the predictive model.
Evaluation:
Analyzed forecast accuracy using confidence intervals and compared it against actual sales.
Key Visualizations
1. Customized Forecast of Sales
Customized Forecast of Sales

Description: Displays the predicted sales over time with historical data and confidence intervals.
Purpose: Highlights how well the model aligns with actual sales trends.
2. Forecast Components
Forecast Components

Trend Component: Illustrates the long-term direction of sales.
Weekly Component: Shows day-of-week sales patterns.
Yearly Component: Captures seasonal fluctuations over the year.
3. Forecasted Sales Over Time
Forecasted Sales OverTime

Description: Compares historical sales data with the forecast, showing predictions over time.
4.Sales Forecast with Uncertainty Intervals
Sales Forecast with Uncertainty Intervals
5.Residuals Over Time
Residuals Over Time
Tools and Technologies
Tableau: For data visualization.
SQL: for data Analysis
SELECT 
  DATEPART(YEAR, ship_date) year,
  DATEPART(QUARTER, ship_date) quarter,
  DATEPART(MONTH, ship_date) month,
  SUM(Sales) total_sales FROM ordersGROUP BY  
  DATEPART(YEAR, ship_date),
  DATEPART(QUARTER, ship_date),
  DATEPART(MONTH, ship_date)
ORDER BY year, quarter, month ASC;
RFM Analysis: Used for customer segmentation.
Data Sources: Sales, shipping, and customer datasets.
Python: For data visualization.
import pandas as pd
data = pd.read_csv('Sales_Dataset.csv')
data['ds'] = pd.to_datetime(data['Order Date'], format='%d/%m/%Y', dayfirst=True)
data['y'] = data['Sales']
data = data[['ds', 'y']]
Facebook Prophet: For time-series prediction.
Matplotlib & Seaborn: For visualizing sales data and model outputs.
Files in this repository:
/data: Contains datasets used in the analysis (raw/cleaned).
/scripts: Python/R scripts for data analysis and cleaning.
/visualizations: Tableau workbook and dashboards.
