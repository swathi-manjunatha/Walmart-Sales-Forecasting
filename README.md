# 📈 Walmart Sales Forecasting – Time Series Analysis

## 📌 Overview
This project focuses on building a time series forecasting model for **Walmart’s weekly sales data** across multiple stores and departments. The objective is to create accurate, data-driven forecasts that help optimize inventory and operations using historical patterns, seasonality, and event-driven factors.

---

## 📊 Dataset
- **Source**: [Walmart Kaggle Dataset](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/data)
- **Records**: ~420,000 weekly sales entries  
- **Time Period**: 2010 – 2012  
- **Features**: Store, Dept, Date, Weekly_Sales, IsHoliday, Temperature, Fuel_Price, CPI, Unemployment

---

## 🔁 Project Workflow

### 1. 🧹 Data Preprocessing
- Merged datasets (features, stores, sales)
- Handled missing values and outliers
- Converted weekly date series to time-based indices

### 2. 📊 Exploratory Data Analysis
- Visualized trends, store-level seasonality, and holiday spikes
- Analyzed effects of CPI, Fuel Prices, and Unemployment on sales
- Correlated external regressors with target variable (Weekly_Sales)

### 3. 📈 Time Series Modeling
- Used **SARIMAX (Seasonal ARIMA with Exogenous Variables)** to model sales  
- Incorporated **holiday flags**, **CPI**, and **Fuel_Price** as external variables  
- Handled non-stationarity and seasonal decomposition  

### 4. ✅ Evaluation
- Performance metrics: **Root Mean Square Error (RMSE)** and **Akaike Information Criterion (AIC)**  
- Visual validation with prediction vs actuals across stores and departments

---

## 📦 Technologies Used
- **Python**: pandas, numpy, matplotlib, seaborn  
- **Modeling**: statsmodels (SARIMAX), scipy, sklearn  
- **Visualization**: seaborn, matplotlib  

---

## 🔍 Key Insights
- Sales exhibit strong **weekly seasonality** and are significantly impacted by **holidays**.  
- SARIMAX performed well in capturing both **trend** and **external factor influence**.  
- Exogenous variables like **CPI** and **Fuel Price** provided improved prediction stability.

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/walmart-sales-forecasting.git
cd walmart-sales-forecasting

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch the notebook
jupyter notebook walmart_sales_forecasting.ipynb
