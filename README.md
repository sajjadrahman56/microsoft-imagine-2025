# Inflation Forecasting Dashboard: Technical Documentation

## **Overview of the Project**
The Inflation Forecasting Dashboard is a web-based tool designed to provide insights into historical and forecasted inflation trends for different regions. Its primary focus is to assist businesses, investors, and policymakers in making informed decisions by visualizing inflation trends and providing tailored investment advice.

This project is designed to align with the objectives of the Imagine Microsoft AI Challenge, focusing on innovative solutions for economic challenges by leveraging advanced AI and data-driven decision-making tools.

---

## **Objectives**
1. **Help Investors and Businesses**:
   - Provide clear inflation trends and forecasts for different regions.
   - Offer tailored investment advice based on inflation rates.
2. **User-Friendly Interactivity**:
   - Allow users to select regions (division or district level).
   - Enable filtering of data by year and dynamically update insights.
3. **Reliability and Scalability**:
   - Ensure accurate inflation forecasting using ARIMA models.
   - Allow for future integration of additional data or features.
4. **Alignment with AI Challenge Goals**:
   - Showcase the practical application of AI in solving real-world economic problems.
   - Demonstrate scalability and real-time responsiveness.

---

## **Key Features**
1. **Historical and Forecasted Inflation Trends**:
   - Visualizes past inflation data and predicts future trends for up to 12 months.
2. **Dynamic Region and Year Selection**:
   - Users can toggle between division and district-level data.
   - Filter historical data dynamically based on the selected year.
3. **Color-Coded Inflation Visualization**:
   - Highlights periods of safe (green), moderate (orange), and high (red) inflation rates.
4. **Investment Insights**:
   - Provides actionable investment advice tailored to inflation trends.
5. **AI Integration**:
   - Utilizes ARIMA models for accurate forecasting.
   - Offers potential for integrating advanced machine learning models (e.g., LSTM) to enhance predictions.

---

## **How It Works**
### **1. Data Sources**
- Two datasets are used:
  - **Division-Level Data:** Aggregated inflation data by division.
  - **District-Level Data:** Raw inflation data at the district level.

### **2. Forecasting Model**
- **ARIMA Model**:
  - Used to forecast inflation rates for the next 12 months.
  - Trained dynamically based on the selected region and filtered historical data.

### **3. Dashboard Components**
- **Region Selector:** Dropdown to choose between division or district-level data.
- **Year Slider:** Filter data dynamically by selecting a specific year.
- **Forecast Graph:**
  - Displays historical data with color-coded inflation levels.
  - Includes forecasted inflation trends.
- **Investment Insights:**
  - Updates dynamically based on the inflation rate for the selected year.

---

## **How to Modify or Update the Dashboard**

### **1. Modify Data Sources**
If you want to update or replace the datasets:
- Replace `division_level_data.csv` and `district_level_data.csv` with new datasets.
- Ensure the following columns are included:
  - `price_date`: Date column in YYYY-MM-DD format.
  - `adm1_name` and `adm2_name`: Division and district identifiers.
  - `inflation_exchange_rate_unofficial`: Inflation rate column.
- Validate the data by running:
  ```python
  print(data.info())
  print(data.head())
  ```

### **2. Adjust Forecasting Model**
- To improve accuracy or add complexity to the forecasting model:
  - Experiment with ARIMA parameters (`p`, `d`, `q`):
    ```python
    model = ARIMA(data['inflation_exchange_rate_unofficial'], order=(2, 1, 2))
    ```
  - Switch to more advanced models like SARIMAX (for external regressors) or LSTM (deep learning).

### **3. Add New Features**
- **Integration with Real-Time Data:**
  - Use APIs from central banks or financial institutions to fetch live inflation data.
- **Enhanced Visualizations:**
  - Add heatmaps for regional comparisons.
  - Integrate interactive maps for geographic visualization of inflation.
- **Investor Recommendations:**
  - Include insights into asset performance (e.g., gold, bonds) during different inflation phases.

### **4. Improve User Interactivity**
- **Dynamic Range Filters:**
  - Add multi-year selection for broader trend analysis.
- **Custom Thresholds:**
  - Allow users to define "safe," "moderate," and "high" inflation thresholds.

---

## **Identified Gaps and Improvements**

### **1. Gaps in Data Granularity**
- **Issue:**
  - Current datasets lack additional economic indicators (e.g., GDP, employment rates) to provide a holistic view.
- **Solution:**
  - Integrate external datasets with more granular economic data.

### **2. Limited Forecasting Scope**
- **Issue:**
  - ARIMA forecasts are limited to 12 months.
- **Solution:**
  - Switch to models like LSTM for longer-term and more complex forecasting.

### **3. Static Investment Advice**
- **Issue:**
  - Investment advice is tailored only to inflation rates.
- **Solution:**
  - Incorporate asset-specific insights (e.g., performance of gold or stocks during high inflation).
  - Allow users to customize advice based on their portfolio preferences.

### **4. No Real-Time Updates**
- **Issue:**
  - The dashboard relies on static datasets.
- **Solution:**
  - Use APIs to fetch real-time inflation data and update forecasts dynamically.

---

## **Making the Dashboard More Reliable for Businesses and Investors**

### **1. Data Validation and Automation**
- Automate data ingestion pipelines to reduce manual errors.
- Validate datasets before model training to ensure consistency.

### **2. Advanced Model Integration**
- Incorporate multivariate models (e.g., SARIMAX) to include external factors like currency exchange rates or commodity prices.
- Use ensemble models to improve prediction reliability.

### **3. Improved Insights for Investors**
- Provide actionable recommendations based on historical asset performance during similar inflation periods.
- Add scenario analysis tools ("What-If" simulations).

### **4. Scalable Deployment**
- Host the dashboard on cloud platforms (e.g., Azure, AWS, Heroku) for wider accessibility.
- Implement user authentication to allow businesses to save custom reports or analysis.

---

## **Conclusion**
The Inflation Forecasting Dashboard is a robust tool for analyzing and predicting inflation trends. By addressing the identified gaps and implementing recommended improvements, it can become an even more reliable resource for businesses and investors, offering real-time insights and advanced forecasting capabilities while aligning with the goals of the Imagine Microsoft AI Challenge.

