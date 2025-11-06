#  Walmart Sales Forecasting

###  Project Overview
This project predicts **weekly sales** for Walmart stores using historical data.  
It demonstrates a complete **data science workflow** — from cleaning to modeling and visualization.

---

###  Datasets
- `train.csv` → Weekly sales per store & department  
- `test.csv` → Data for prediction  
- `features.csv` → Economic indicators (CPI, Unemployment, Fuel_Price, etc.)  
- `stores.csv` → Store metadata (Type, Size)

---

###  Data Preprocessing
- Merged all datasets on `Store` and `Date`.
- Filled missing `MarkDown` values with 0.
- Removed outliers using Z-score.
- Converted `Date` to datetime and extracted week, month, year.

---

###  Exploratory Data Analysis (EDA)
- Correlation heatmap of numeric features.
- Weekly/Monthly trend analysis.
- Impact of holidays on sales.
- Visualization of store and department performance.

---

###  Feature Engineering
- Lag features: `Weekly_Sales_lag_1` ... `lag_4`
- Rolling windows: mean, std, min, max (7, 14, 28 days)
- Exponential moving averages & expanding stats
- Encoded categorical variables (Store Type)

---

###  Modeling
- **Model:** Linear Regression  
- **Metrics:** RMSE, MAE, R² Score  
- **Scaler:** MinMaxScaler

---


Visualizations show that sales spikes align with holidays (e.g., Black Friday, New Year).

---

###  Saving Models
Models and scalers saved using:
```python
joblib.dump(scaler, "models/minmax_scaler.pkl")
joblib.dump(lr, "models/linear_regression.pkl")
