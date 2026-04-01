# Demand Forecasting Project

This project uses retail sales data to forecast product demand and translate the forecast into inventory decisions. Instead of stopping at model accuracy, it connects prediction output to safety stock and reorder point planning.

Portfolio hub: [Mindeulaeggot/data-analytics-portfolio](https://github.com/Mindeulaeggot/data-analytics-portfolio)

This project is positioned to support both data analytics internship applications and SCM internship applications because it combines model evaluation with supply chain decision-making.

## 1. Problem

Retail operations face two costly risks:

- understocking, which causes stockouts and lost sales
- overstocking, which increases holding cost and waste

The goal of this project is to predict future demand and show how forecasting can support better inventory planning.

## 2. Data

- Source file: `data/retail_sales.csv`
- Time range: `2019-01-01` to `2023-12-31`
- Scale: about `4.57 million` rows
- Coverage: `50` stores and `50` items
- Example forecasting case: `store_1 / item_1`

## 3. Method

The workflow is split into three notebooks:

1. [01_eda.ipynb](./notebooks/01_eda.ipynb)
   Explores sales patterns, seasonality, and data quality.
2. [02_forecasting.ipynb](./notebooks/02_forecasting.ipynb)
   Compares baseline forecasting, Linear Regression, and Random Forest.
3. [03_inventory_policy.ipynb](./notebooks/03_inventory_policy.ipynb)
   Converts predicted demand into safety stock and reorder point recommendations.

Main methods used:

- exploratory data analysis
- feature engineering for time-based demand patterns
- Linear Regression
- Random Forest
- MAE and RMSE for forecast evaluation
- inventory policy logic using lead time and service level assumptions

## 4. Result

Example results for `store_1 / item_1`:

| Metric | Result |
|---|---:|
| Baseline MAE | `11.73` |
| Linear Regression MAE | `7.33` |
| Random Forest MAE | `3.64` |
| Lead Time | `7 days` |
| Service Level | `~95%` |
| Safety Stock | `60.46` |
| Reorder Point | `386.58` |

## 5. Insight

- The Random Forest model substantially outperformed the baseline forecast on the sample series.
- Demand forecasting became more useful once it was converted into an inventory decision rule.
- The project shows that analytics value comes not only from prediction quality, but from how the prediction changes an operational decision.

## Why This Works As a Portfolio Project

- It shows a clear business problem, not just a model.
- It uses a large real-world style retail dataset.
- It includes measurable model improvement.
- It ends with business actions: safety stock and reorder point.

For data analytics roles, it shows exploratory analysis, model comparison, and quantitative evaluation.

For SCM roles, it shows how analytics can inform inventory planning, reorder decisions, and operational tradeoffs.

## Tech Stack

- Python
- pandas
- numpy
- matplotlib
- scikit-learn
- Jupyter Notebook

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

## How To Run

```bash
pip install -r requirements.txt
```

Then run the notebooks in this order:

1. `notebooks/01_eda.ipynb`
2. `notebooks/02_forecasting.ipynb`
3. `notebooks/03_inventory_policy.ipynb`

## Resume Bullet Version

- Built a retail demand forecasting project on `4.57M+` sales records and compared baseline, Linear Regression, and Random Forest models.
- Reduced MAE from `11.73` to `3.64` on a sample store-item series.
- Translated forecast output into inventory recommendations through safety stock and reorder point analysis.

## Next Upgrade

- expand from one sample series to multiple store-item combinations
- compare with stronger time-series-specific models
- add cost-based inventory tradeoff analysis
