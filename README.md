# Demand Forecasting and Inventory Optimization for SCM

## Project Overview
This project uses retail sales data to connect **demand forecasting** with **inventory policy** decisions.
The goal is to show how data analysis can support Supply Chain Management (SCM) by forecasting demand,
estimating uncertainty, and calculating safety stock and reorder points.

## Dataset
- File: `retail_sales.csv`
- Period: 2019-01-01 to 2023-12-31
- Rows: 4,565,000
- Stores: 50
- Items: 50

## Project Structure
```text
scm_demand_forecast_project/
├── data/
│   └── retail_sales.csv
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_forecasting.ipynb
│   └── 03_inventory_policy.ipynb
├── requirements.txt
└── README.md
```

## Workflow
1. **EDA**
   - Understand sales trends, seasonality, and sample store-item behavior
2. **Forecasting**
   - Compare baseline, Linear Regression, and Random Forest models
3. **Inventory Policy**
   - Calculate safety stock and reorder point using predicted demand

## Main Result (example: store_1 / item_1)
- Baseline MAE: **11.73**
- Linear Regression MAE: **7.33**
- Random Forest MAE: **3.64**
- Recommended safety stock (7-day lead time, ~95% service level): **60.46**
- Recommended reorder point: **386.58**

## Resume Bullet
**Demand Forecasting and Inventory Optimization for SCM (Python)**  
- Built demand forecasting models using retail sales data and analyzed store-item sales patterns  
- Calculated safety stock and reorder point based on forecasted demand variability and lead time assumptions  
- Connected machine learning outputs to inventory decision-making in an SCM-focused project

## Notes
- The notebooks are written to be simple, readable, and resume-friendly.
- Put `retail_sales.csv` inside the `data/` folder before running.
