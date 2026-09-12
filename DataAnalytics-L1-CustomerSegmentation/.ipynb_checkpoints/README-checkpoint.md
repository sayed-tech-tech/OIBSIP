# Task 2 – Customer Segmentation using K-Means Clustering

## Overview
This project segments mall customers into distinct groups based on their 
Annual Income and Spending Score, using K-Means clustering. The goal is to 
identify customer types to enable targeted marketing strategies.

## Dataset
- **Source:** Kaggle (Mall Customer Segmentation Data)
- **File:** `mall_customers.csv` — 200 rows, 5 columns
- No missing values; no cleaning required.

## Approach
1. Explored the relationship between Annual Income and Spending Score visually
2. Used the **Elbow Method** to determine the optimal number of clusters 
   (k=5, identified by the bend in the inertia curve)
3. Applied **K-Means clustering** (scikit-learn) with k=5
4. Visualized and interpreted the resulting customer segments

## Key Findings
5 distinct customer segments were identified:
- High income, high spending (best customers)
- High income, low spending (untapped potential)
- Low income, high spending (impulsive spenders)
- Low income, low spending (budget-conscious)
- Average income, average spending (largest, typical group)

See notebook for full breakdown and business recommendations per segment.

## Tools Used
Python, pandas, scikit-learn (KMeans), matplotlib, seaborn, Jupyter Notebook

## Author
Syed Touheed Shah — Data Analytics Intern, Oasis Infobyte (OIBSIP)