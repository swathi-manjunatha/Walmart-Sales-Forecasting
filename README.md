# 📈 Walmart Sales Forecasting – Machine Learning Model Comparison

## 📌 Overview
This project forecasts weekly sales for Walmart stores using historical data and multiple machine learning models. The objective is to enable accurate prediction of weekly sales across different stores and departments, helping optimize **inventory**, **staffing**, and **promotions**. Models were evaluated with higher sensitivity to **holiday periods**, where accurate forecasting is crucial.

---

## 📊 Dataset
- **Source**: [Kaggle – Walmart Store Sales Forecasting](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting)
- **Size**: ~420,000 records  
- **Features**: Store, Dept, Date, Weekly_Sales, IsHoliday, Temperature, Fuel_Price, CPI, Unemployment  
- **Time Range**: 2010–2012  

---

## 🔁 Workflow Summary

### 1. 🧹 Data Preprocessing
- Merged multiple CSVs (`stores.csv`, `features.csv`, `train.csv`)
- Extracted **datetime-based features** (year, month, week)
- Created **lag features** and **3-week rolling averages**
- Applied **RobustScaler** to handle outliers
- Transformed store types into numerical format

### 2. 📊 Exploratory Data Analysis
- Identified **holiday spikes** and **seasonal sales trends**
- Analyzed influence of **external factors** (e.g., fuel price, CPI)
- Discovered high variance in larger stores and seasonal categories

### 3. 🤖 Model Building
- Implemented:
  - **Linear Regression**
  - **Random Forest Regressor**
- Randomly assigned test samples into **control** and **treatment** groups for model comparison
- Holiday weeks assigned **5x error weights** using **Weighted Mean Absolute Error (WMAE)**

### 4. ✅ Model Evaluation
- Compared models using:
  - **WMAE** (Weighted Mean Absolute Error)
  - **T-Test** for statistical significance
- Prioritized holiday weeks due to their operational importance

---

## 📈 Results

| Model               | WMAE Score     | Notes                              |
|--------------------|----------------|-------------------------------------|
| Linear Regression   | ~22,000        | Baseline model                     |
| Random Forest       | ~18,000        | Lower error & better performance   |

> 📊 **Conclusion**: Random Forest outperformed Linear Regression with a **statistically significant difference (p < 0.05)**. It’s recommended for production use due to its robustness in handling seasonal spikes and feature interactions.

---

## 🧰 Tech Stack
- **Language**: Python  
- **Libraries**: pandas, numpy, matplotlib, seaborn, scikit-learn, scipy  
- **Evaluation**: Weighted MAE, T-Test

---

## 🚀 How to Run

```bash
# Clone the repository
git clone https://github.com/your-username/walmart-sales-forecasting.git
cd walmart-sales-forecasting

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook walmart_sales_forecasting.ipynb
