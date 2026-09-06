# Task 1 – Exploratory Data Analysis: Retail Sales Dataset

## Overview
This project performs exploratory data analysis (EDA) on a retail sales 
dataset (4,310 rows, 21 columns) covering orders from 2020-2024. The goal 
was to uncover trends in sales, identify data quality issues, and surface 
actionable business insights through visualization.

## Dataset
- **Source:** Kaggle (retail sales dataset)
- **File:** `retail_sales_dataset.csv` — 4,310 rows, 21 columns
- **Key columns:** order_date, product_category, region, sales_amount, 
  profit, discount_pct, customer_satisfaction, return_flag, order_status

## Data Cleaning
- Dropped 30 fully-blank rows (all fields null — no recoverable data)
- Filled missing `age`, `quantity`, `days_to_ship` with column median
- Filled missing `discount_pct` with 0 (assumed no discount recorded)
- Left `customer_satisfaction` nulls untouched (invented scores would 
  distort the metric — excluded from that specific analysis instead)
- Converted `order_date` to proper datetime (handled mixed date formats)
- Normalized `order_status` casing (merged duplicate categories like 
  "Delivered"/"delivered")

## Analysis & Visualizations
1. **Monthly sales trend** — line chart across 2020-2024
2. **Sales by product category** — bar chart
3. **Sales by region** — bar chart
4. **Correlation heatmap** — numeric feature relationships
5. **Order status breakdown** — bar chart
6. **Return rate by category** — grouped analysis

## Key Insights
1. Electronics dominates revenue (~$157M), 2.7x the next category (Furniture)
2. Two anomalous sales spikes: January 2023 (~$19M) and April 2021 (~$11.8M)
3. Regional sales are relatively balanced (South leads, but no single 
   region dominates like Electronics does among categories)
4. Discount percentage shows near-zero correlation with sales/profit (-0.05), 
   suggesting the current discount strategy isn't driving purchases
5. Sales and profit are highly correlated (0.95) — costs scale predictably
6. Overall return rate is 14.56%, and consistent across all categories 
   (13.5%-16%), pointing to a systemic issue rather than a category-specific one

## Tools Used
Python, pandas, matplotlib, seaborn, Jupyter Notebook

## Author
Syed Touheed Shah — Data Analytics Intern, Oasis Infobyte (OIBSIP)