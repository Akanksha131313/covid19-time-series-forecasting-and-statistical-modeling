**COVID-19 State-wise Reporting Module -**

Generates actionable state-wise COVID-19 summary reports and visualizations for India.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

**📌 Purpose -**

Provides **insightful, actionable reports** of COVID-19 metrics per State/UT to support **policy decisions, healthcare planning, and resource allocation**.  
Includes a clear **snapshot of high-risk states** based on total cases, deaths, and active cases.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

**📊 Dataset -**

- Source: `India_COVID19_Statewise_TimeSeries_Analytics_2021.csv`

- Columns used:  

  `Date`, `State_UT`, `Population`, `New_Cases`, `New_Deaths`, `New_Recoveries`, `Total_Cases`, `Total_Deaths`, `Total_Recoveries`, `Active_Cases`

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

**🛠 Approach -**

1. Load the cleaned CSV dataset with **error handling**. 

2. Aggregate **state-wise summary metrics**:

   - Total Cases, Total Deaths, Active Cases, Total Recoveries  

   - Maximum daily New Cases, Deaths, and Recoveries 

3. Identify **top 3 states per key metric** (Total Cases, Active Cases, Total Deaths) and print **actionable insights** in console. 

4. Generate **state-wise visualizations** of COVID-19 trends: 

   - Total Cases, Active Cases, Total Recoveries, Total Deaths 

5. **Optional Forecast Integration**:

   - Placeholder to overlay forecasted Total Cases from `07_forecasting` outputs:  

     ```python

     forecast_df = pd.read_csv(f"forecasts/forecast_{state.replace(' ','_')}.csv")

     plt.plot(forecast_df['ds'], forecast_df['yhat'], label='Forecasted Total Cases', linestyle='--')
     ```  
   - Enables future trend visualization alongside historical data.  

6. Save **summary CSV** and **state-wise PNG plots** in `reports/`.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

** 📈 Output -**

- `reports/statewise_summary.csv` → state-wise aggregated metrics  

- `reports/report_<State_UT>.png` → time-series visualizations for each state  

- Console output showing **top 3 high-risk states** per metric  

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

**💡 Impact -**

- Highlights states with **highest COVID-19 risk**, helping policymakers prioritize resources.

- Converts raw COVID-19 data into **interpretable, actionable insights**. 

- Ready for **integration with forecasts**, giving a **forward-looking view** of the pandemic.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

**🔧 Technologies -**

- Python 3.x  

- Pandas  

- Matplotlib  

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

**🚀 Next Steps / Optional Enhancements -** 

- Integrate actual forecast outputs from `07_forecasting` to visualize predicted trends. 

- Add interactive dashboards (Plotly/Streamlit) for **dynamic exploration**. 

- Extend reporting to multiple metrics beyond total cases (e.g., growth rates, rolling averages).  

