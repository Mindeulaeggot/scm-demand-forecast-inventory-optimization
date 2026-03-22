# Demand Forecasting and Inventory Optimization for SCM

This project shows how retail sales data can be used to connect **demand forecasting** with **inventory policy** decisions in a supply chain context. The workflow moves from exploratory analysis to forecasting, then converts predicted demand into safety stock and reorder point recommendations.

## Why This Project Matters

In SCM, forecasting is only useful if it improves operational decisions. This project demonstrates that connection by:

- analyzing sales patterns and seasonality
- comparing forecasting models on a sample store-item series
- translating forecast output into inventory control metrics

## Dataset

- File: `data/retail_sales.csv`
- Period: `2019-01-01` to `2023-12-31`
- Rows: about `4.57 million`
- Stores: `50`
- Items: `50`

## Repository Structure

```text
scm-demand-forecast-inventory-optimization/
|-- data/
|   |-- retail_sales.csv
|   `-- PUT_RETAIL_SALES_CSV_HERE.txt
|-- notebooks/
|   |-- 01_eda.ipynb
|   |-- 02_forecasting.ipynb
|   `-- 03_inventory_policy.ipynb
|-- requirements.txt
`-- README.md
```

## Workflow

1. `01_eda.ipynb`
   - explore data shape, missing values, and time patterns
   - visualize total daily sales, monthly behavior, and a sample store-item series
2. `02_forecasting.ipynb`
   - build baseline, Linear Regression, and Random Forest forecasting models
   - compare model performance with MAE and RMSE
   - plot actual versus predicted demand
3. `03_inventory_policy.ipynb`
   - use forecasted demand to estimate average demand and variability
   - calculate safety stock and reorder point
   - connect ML output to inventory planning decisions

## Main Result

Example result for `store_1 / item_1`:

- Baseline MAE: `11.73`
- Linear Regression MAE: `7.33`
- Random Forest MAE: `3.64`
- Lead time assumption: `7 days`
- Service level assumption: about `95%`
- Recommended safety stock: `60.46`
- Recommended reorder point: `386.58`

## Tools

- Python
- pandas
- numpy
- matplotlib
- scikit-learn
- Jupyter Notebook

## How To Run

```bash
pip install -r requirements.txt
```

Then open the notebooks in order:

1. `notebooks/01_eda.ipynb`
2. `notebooks/02_forecasting.ipynb`
3. `notebooks/03_inventory_policy.ipynb`

## Resume-Ready Bullets

- Built an SCM-focused demand forecasting project using retail sales data, comparing baseline, Linear Regression, and Random Forest models on a store-item demand series.
- Reduced forecast error from `11.73` MAE with a baseline model to `3.64` MAE with Random Forest, then used forecast outputs for inventory planning.
- Calculated safety stock and reorder point recommendations from predicted demand variability and lead time assumptions to connect analytics with supply chain decisions.

## Notes

- The project is notebook-based and designed to be easy to review on GitHub.
- The dataset is tracked with Git LFS because of file size.
- The forecasting example is intentionally scoped to a sample `store_1 / item_1` case for clarity and speed.
