# Walmart-Sales-Forecasting-using-Random-Forest-Modeling



# Walmart Sales Forecasting Project

## **Overview**
This project focuses on predicting weekly sales for Walmart stores using machine learning techniques. The aim is to analyze seasonal trends, especially during holiday weeks, and optimize inventory planning, revenue forecasting, and decision-making strategies.

---

## **Problem Statement**
Walmart experiences significant sales fluctuations during holiday seasons. Accurately forecasting these variations is critical for:
- Inventory management
- Revenue prediction
- Strategic decision-making

### **Key Challenges**
1. Seasonal sales variations due to holidays.
2. Handling missing data and encoding categorical features.
3. Incorporating holiday impacts into predictive models.

---

## **Objectives**
- Build a robust machine learning model to forecast weekly sales.
- Analyze the impact of holidays on sales performance.
- Provide actionable insights to improve operational efficiency.

---

## **Dataset Overview**
The project utilizes the following datasets:
- **Train Dataset**: Weekly sales data for Walmart stores.
- **Features Dataset**: Additional data such as fuel price, CPI, temperature, markdowns, and holiday indicators.
- **Stores Dataset**: Metadata about store types and sizes.

### **Key Features**
- **Dept**: Department number.
- **Store**: Store ID.
- **Date**: Week ending date.
- **Weekly_Sales**: Weekly sales amount (target variable).
- **IsHoliday**: Boolean flag indicating if the week includes a holiday.
- **MarkDowns**: Promotional discount data.

---

## **Methodology**

### **1. Data Preprocessing**
- Merged datasets on relevant keys (`Store` and `Date`).
- Handled missing values (e.g., filled `MarkDown` columns with `0`).
- Feature engineering:
  - Extracted `Year`, `Month`, `Week`, and `Day` from the `Date` column.
  - Encoded categorical variables (`Type` and `IsHoliday`).

### **2. Model Development**
- **Random Forest Regressor**:
  - Tuned hyperparameters (`n_estimators`, `max_depth`) manually.
  - Evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and Weighted Mean Absolute Error (WMAE).

### **3. Evaluation Metrics**
- **WMAE**: Weighted error metric emphasizing the importance of holiday weeks.
- **MAE, MSE, RMSE**: Standard metrics for measuring model accuracy.

### **4. Visualizations**
- **Feature Importance**: Identified the most significant predictors.
- **Sales Trends**: Plotted weekly and monthly trends to uncover seasonal patterns.

---

## **Results**

### **Model Performance**
- Achieved a Weighted Mean Absolute Error (WMAE) of **4,485** using the Random Forest Regressor.
- Additional evaluation metrics included:
  - **Mean Absolute Error (MAE)**: Measures the average magnitude of errors.
  - **Mean Squared Error (MSE)**: Penalizes larger errors by squaring them.
  - **Root Mean Squared Error (RMSE)**: Offers a standard interpretation in the same units as sales.

### **Key Predictors Identified**
- **Top Features by Importance**:
  1. `Dept`: Department-level differences significantly impacted sales.
  2. `Store`: Variations in store performance highlighted regional trends.
  3. `Week`: Seasonal and weekly patterns were critical for accurate forecasting.
  4. `Type`: Store type (`A`, `B`, `C`) influenced overall sales volume.
  5. `IsHoliday`: Sales spikes during holiday weeks reinforced the need for weighted metrics.
  6. `Size`: Larger stores consistently drove higher revenue.

### **Sales Trends and Insights**
- **Holiday Impacts**:
  - Sales during holidays such as **Thanksgiving** and **Christmas** peaked substantially, with Thanksgiving being a standout week.
  - Holiday-driven spikes necessitate strategic inventory planning and demand forecasting.
  - Post-holiday periods, particularly in **January**, showed predictable declines, emphasizing the need for seasonal adjustments.

- **Store Performance**:
  - **Type A Stores** (large) consistently outperformed smaller stores (Types B and C) across all weeks, emphasizing the correlation between store size and sales potential.
  - Regional and size-based variations suggest opportunities for tailored marketing strategies.

- **Department-Level Observations**:
  - Departments exhibited varying degrees of seasonal sales spikes.
  - Some departments experienced high variability, particularly during promotional markdowns and holidays, underlining the importance of department-specific planning.

### **Visual Insights**
- **Feature Importance**:
  - Random Forest analysis ranked `Dept`, `Store`, and `Week` as the most critical features.
  - Visualizing feature importance provided actionable insights for focusing business strategies.

- **Sales Trends**:
  - **Weekly Trends**: Line plots revealed clear seasonal patterns, including holiday-driven spikes and dips.
  - **Monthly Trends**: Bar charts highlighted periods of high activity (e.g., Q4) and low activity (e.g., January).

---

## **Business Recommendations**
1. **Focus on Holiday Weeks**:
   - Allocate additional inventory and staffing resources during peak weeks like Thanksgiving and Christmas.
   - Introduce targeted marketing campaigns for holidays to capitalize on sales opportunities.

2. **Leverage Store Type Data**:
   - Tailor inventory strategies based on store size and regional performance to optimize operations.

3. **Refine Department Strategies**:
   - Analyze high-performing departments and apply focused promotions to sustain growth.

4. **Future Enhancements**:
   - Incorporate additional features like local events or economic indicators to refine forecasting.
   - Implement time-series models (e.g., ARIMA, SARIMA) to complement machine learning predictions.
   - Advanced Modeling - Combine the strengths of machine learning (Random Forest) and time-series forecasting into a hybrid model for improved  accuracy.


---

## **Technologies Used**
- **Programming Language**: Python
- **Libraries**:
  - `pandas`, `numpy`: Data manipulation
  - `matplotlib`, `seaborn`: Visualization
  - `scikit-learn`: Machine learning
  - `statsmodels`: Time-series analysis (optional for future enhancements)

---

## **How to Run the Project**
1. Clone the repository:
   ```bash
   git clone <repository-link>
   ```
2. Install required libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook:
   ```bash
   jupyter notebook "Walmart Sales Forecasting.ipynb"
   ```

---

## **Project Directory Structure**
```
Walmart-Sales-Forecasting/
|
|-- train.csv               # Sales data
|-- features.csv            # Features data
|-- stores.csv              # Stores metadata
|-- Walmart Sales Forecasting.ipynb # Main project notebook
|-- README.md               # Project documentation
|-- requirements.txt        # Required Python packages
```

---

## **Acknowledgments**
- Walmart for providing the datasets.
- Open-source Python libraries for enabling data analysis and modeling.

