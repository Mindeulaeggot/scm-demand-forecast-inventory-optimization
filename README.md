# Demand Forecasting and Inventory Optimization for SCM

This project shows how retail sales data can be turned into practical supply chain decisions. It starts with exploratory analysis, builds forecasting models for a sample store-item series, and then converts the predicted demand into inventory planning metrics such as safety stock and reorder point.

## Project Snapshot

- Domain: supply chain management, retail analytics
- Dataset: `data/retail_sales.csv`
- Time range: `2019-01-01` to `2023-12-31`
- Scale: about `4.57 million` rows across `50` stores and `50` items
- Focus case: `store_1 / item_1`

## Business Goal

Forecasting is only useful if it improves decisions. This project connects machine learning output to inventory policy by answering three practical questions:

1. What demand patterns and seasonality appear in the sales data?
2. Which forecasting approach performs best on a sample retail series?
3. How can predicted demand be translated into reorder decisions?

## Notebook Guide

Review the notebooks in order on GitHub:

1. [01_eda.ipynb](./notebooks/01_eda.ipynb)
   Explores dataset quality, time patterns, monthly behavior, and a sample demand series.
2. [02_forecasting.ipynb](./notebooks/02_forecasting.ipynb)
   Compares a baseline model, Linear Regression, and Random Forest using MAE and RMSE.
3. [03_inventory_policy.ipynb](./notebooks/03_inventory_policy.ipynb)
   Uses forecast output to calculate safety stock and reorder point recommendations.

## Key Results

Example results for `store_1 / item_1`:

| Metric | Result |
|---|---:|
| Baseline MAE | `11.73` |
| Linear Regression MAE | `7.33` |
| Random Forest MAE | `3.64` |
| Lead Time Assumption | `7 days` |
| Service Level Assumption | `~95%` |
| Safety Stock | `60.46` |
| Reorder Point | `386.58` |

## Why It Matters

- Shows an end-to-end analytics workflow instead of an isolated model.
- Connects forecasting performance to inventory control decisions.
- Keeps the example simple enough to review quickly while still reflecting an SCM use case.

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

Then execute the notebooks in this order:

1. `notebooks/01_eda.ipynb`
2. `notebooks/02_forecasting.ipynb`
3. `notebooks/03_inventory_policy.ipynb`

## Resume-Ready Highlights

- Built an SCM-focused demand forecasting workflow using retail sales data and compared baseline, Linear Regression, and Random Forest models.
- Reduced forecast error from `11.73` MAE with a baseline approach to `3.64` MAE with Random Forest on a sample store-item series.
- Translated forecast output into inventory recommendations by calculating safety stock and reorder point under lead-time and service-level assumptions.

## Notes

- The notebooks now contain executed outputs, so GitHub can render charts and results directly.
- The dataset is tracked with Git LFS because of file size.
- The modeling example is intentionally scoped to a single store-item case for clarity and review speed.
