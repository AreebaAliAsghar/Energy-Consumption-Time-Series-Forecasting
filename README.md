# 📈 Household Energy Consumption — Time Series Forecasting

## 🎯 Objective

Forecast short-term household energy usage using historical time series data.  
Apply and compare statistical models and machine learning approaches to predict daily energy consumption, evaluate performance, and visualize forecasts.

---

## 📂 Dataset Description

- **Dataset Source:** [UCI Machine Learning Repository — Household Power Consumption](https://archive.ics.uci.edu/ml/datasets/individual+household+electric+power+consumption)
- **Data Period:** December 2006 – November 2010
- **Frequency:** 1-minute intervals (resampled to daily for this task)

### Main Features Used:
| Feature | Description |
|---------|-------------|
| Global_active_power | Total active power consumed (kilowatts) |
| Date | Date of measurement |
| Time | Time of measurement |

---

## 🛠️ Project Workflow

### 1️⃣ Data Loading & Cleaning
- Merged `Date` and `Time` into a single `datetime` field  
- Handled missing values represented by `?`  
- Converted numeric columns to float  
- Resampled data to daily averages for meaningful analysis  

---

### 2️⃣ Exploratory Data Analysis (EDA)
- Visualized consumption trends over time  
- Identified weekly patterns and seasonal fluctuations  
- Detected anomalies and missing data points  

---

### 3️⃣ Feature Engineering
- Extracted time-based features:
  - `day_of_week` (0=Monday, 6=Sunday)
  - `month` (1-12)
  - `year`  
- These features were used in machine learning models  

---

### 4️⃣ Model Building & Forecasting

| Model   | Approach | Strengths |
|---------|----------|------------|
| **ARIMA** | Statistical Time Series Model | Good for baseline predictions |
| **Prophet** | Decomposable Time Series Model | Captures trend & seasonality |
| **XGBoost Regressor** | Machine Learning | Best short-term forecast with engineered features |

---

### 5️⃣ Model Evaluation Metrics
- **Mean Absolute Error (MAE)** — Measures average prediction error  
- **Root Mean Squared Error (RMSE)** — Penalizes larger errors  
- Compared all models on these metrics  

---

### 6️⃣ Visualization of Results
- Line plots of **Actual vs Forecasted Energy Consumption**
- Prophet's trend and seasonal component visualizations
- XGBoost’s prediction plotted against real data

---

## 📊 Results & Findings

| Model   | MAE | RMSE |
|---------|-----|------|
| ARIMA  | Moderate | Moderate |
| Prophet| Good | Good |
| XGBoost| **Best** | **Best** |

- **XGBoost with time-based features gave the lowest MAE and RMSE**
- Prophet successfully modeled seasonality and trends
- ARIMA struggled with complex seasonality compared to ML models

---

## 🔥 Key Insights
- Household energy consumption follows clear weekly and seasonal cycles  
- Machine learning models like **XGBoost** benefit from feature engineering and outperform traditional statistical models for short-term forecasting  
- Accurate forecasting enables better planning for energy providers and consumers  


---

## 🧩 Tools & Libraries Used

- **Data Handling:** pandas, numpy  
- **Visualization:** matplotlib, seaborn  
- **Statistical Models:** statsmodels (ARIMA), Prophet  
- **Machine Learning:** xgboost, scikit-learn  

---

## 📝 Conclusion & Takeaways

> Time series forecasting is essential for understanding consumption patterns.  
> This project shows that combining feature engineering with machine learning models (XGBoost) can lead to superior forecasting results compared to traditional models like ARIMA.  
> With better predictions, energy providers can optimize supply, and consumers can make informed usage decisions.

---

