# Sales Data Analysis and Forecasting Project

## Project Overview
This project involves analyzing historical sales data to uncover trends and forecast future sales using ARIMA models. The goal was to integrate cloud technologies and data science skills to create a comprehensive solution for time series analysis, including data extraction, preprocessing, visualisation, machine learning, and model evaluation. The analysis highlights key sales trends and provides actionable insights into the future performance of the business.

### Objectives
- Extract sales data stored in a PostgreSQL database hosted on AWS RDS.
- Perform exploratory data analysis (EDA) to understand sales trends.
- Apply data preprocessing techniques to prepare the dataset for time series modeling.
- Use ARIMA models to forecast future sales trends.
- Visualise historical and forecasted data.
- Host results on AWS Quicksight for dashboarding and sharing insights.

---

## Key Skills Demonstrated

### **Cloud Integration**
- **AWS RDS**: Managed a PostgreSQL database instance on AWS RDS to store and retrieve sales data.
- **AWS Quicksight**: Built a dashboard to visualize sales trends and forecasted results.
- **AWS S3**: Used for storing and accessing processed datasets.

### **Data Engineering**
- SQL skills to extract and aggregate sales data from a relational database.
- Data preprocessing including sorting, handling duplicate dates, and resampling data to monthly levels.
- Integration of SQLAlchemy with Python for seamless database connectivity.

### **Data Science and Machine Learning**
- Performed exploratory data analysis (EDA) using `pandas` and `matplotlib` to identify trends and anomalies.
- Stationarity tests (ADF test) to validate the suitability of the data for time series modeling.
- ARIMA modeling for forecasting future sales.
- Model evaluation using metrics like MAE and RMSE.

### **Visualisation**
- Developed visualizations to depict daily and monthly sales trends using `matplotlib`.
- Displayed forecasted sales alongside historical data.
- Created interactive dashboards in AWS Quicksight for sharing insights with stakeholders.

---

## Project Workflow

### **1. Data Extraction**
- The sales data was stored in an AWS RDS PostgreSQL instance.
- SQLAlchemy was used to connect to the database and execute queries to retrieve sales data grouped by order date.

### **2. Data Preprocessing**
- Checked for duplicate and unsorted dates to ensure data quality.
- Resampled daily sales data to monthly totals for easier trend analysis.
- Converted date columns to datetime objects for time series processing.

### **3. Exploratory Data Analysis (EDA)**
- Visualized daily and monthly sales trends to understand seasonality and cyclical patterns.
- Identified significant sales spikes and trends in the historical data.

### **4. Stationarity Testing**
- Conducted Augmented Dickey-Fuller (ADF) tests to check for stationarity in both daily and monthly sales data.
- Confirmed that the data was stationary, making it suitable for ARIMA modeling.

### **5. Time Series Modelling**
- Applied ARIMA (1, 0, 1) models to monthly sales data.
- Forecasted sales for the next 12 months.

### **6. Model Evaluation**
- Evaluated the ARIMA model using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE):
  - **MAE**: 18,962
  - **RMSE**: 24,280

### **7. Visualisation and Dashboarding**
- Visualized forecasted sales against historical data using `matplotlib`.
- Uploaded forecasted results to AWS Quicksight to create an interactive dashboard showing:
  - Historical trends.
  - Forecasted sales for the next 12 months.
  - Regional and categorical breakdowns of sales performance.

---
### Data Preparation and Loading

S3 bucket creation and data upload:

<img width="2042" alt="Xnapper-2024-12-19-22 38 38" src="https://github.com/user-attachments/assets/edd496b0-ad6a-414e-a2bd-18849fa730bb" />
<img width="1797" alt="Xnapper-2024-12-19-22 42 26" src="https://github.com/user-attachments/assets/d1f79b15-c7e4-4192-a0af-8a1b654cc00e" />
<img width="1790" alt="Xnapper-2024-12-19-22 43 25" src="https://github.com/user-attachments/assets/b0f03c43-df99-43e5-8e5e-4f4ccfc76353" />
<img width="1794" alt="Xnapper-2024-12-19-22 44 11" src="https://github.com/user-attachments/assets/80b745c0-0ea0-49a7-83f9-bf4a8f5bbda8" />


RDS database creation and data loading:

<img width="1746" alt="Xnapper-2024-12-19-22 44 38" src="https://github.com/user-attachments/assets/49ae2038-4fe5-4445-a518-7540a515e1c6" />
<img width="1718" alt="Xnapper-2024-12-19-22 45 11" src="https://github.com/user-attachments/assets/25ed7935-f87d-48dc-8dc9-fb63dac163b7" />

### Exploratory Data Analysis

SQL query outputs from psql:

<img width="806" alt="Xnapper-2024-12-19-22 45 54" src="https://github.com/user-attachments/assets/3aa67553-27dc-42a7-a101-f3234486d15a" />
<img width="1184" alt="Xnapper-2024-12-19-22 47 53" src="https://github.com/user-attachments/assets/0192af68-ca08-4fc9-948f-9ccd5d44d052" />
<img width="1154" alt="Xnapper-2024-12-19-22 49 39" src="https://github.com/user-attachments/assets/b8e770fd-6d02-48c9-98ea-63cbb7472c7b" />
<img width="2028" alt="Xnapper-2024-12-19-23 14 32" src="https://github.com/user-attachments/assets/9efa3754-8ccd-45ce-98de-5bf6515520f2" />
<img width="2028" alt="Xnapper-2024-12-19-23 16 04" src="https://github.com/user-attachments/assets/14a403c1-cbba-43c3-976a-06af63150d27" />

Description of columns and the dataset:

<img width="1024" alt="Xnapper-2024-12-19-22 50 18" src="https://github.com/user-attachments/assets/6a57eb0c-92c5-4910-9072-a8598bd06c49" />

### Visualisation and Analysis

Daily and monthly sales trends graphs:

![Xnapper-2024-12-19-23 04 30](https://github.com/user-attachments/assets/57b4032e-9d34-4a47-bf4e-8e24fa7315b3)

#### Insights from charts:

Daily Sales Over Time:

The daily sales graph seems highly volatile, with significant spikes indicating occasional high-value transactions.
These spikes might represent promotional events, bulk purchases, or seasonal trends. The variability highlights the need for aggregating data (e.g., monthly) to identify clearer trends.

Monthly Sales Over Time:

The monthly aggregated sales show a clear cyclical pattern, with periodic rises and falls. There is an overall upward trend in sales over the years, suggesting growth in business performance. The aggregation smooths out daily fluctuations, making it easier to observe seasonal or annual patterns.

### Machine Learning Forecasting

#### Stationary Test (ADF Test):

![Xnapper-2024-12-19-23 09 19](https://github.com/user-attachments/assets/5d7ff93f-2a32-4266-a304-09439b85bda2)

ARIMA model training outputs:

![Xnapper-2024-12-19-23 09 52](https://github.com/user-attachments/assets/1da9814f-c979-4bd6-b83f-b6a45599edba)

Evaluation metrics and their interpretations:

#### ADF Statistic:

For the daily data: -5.8395, much lower than the critical values (-3.43, -2.86, -2.56).
For the monthly data: -4.4937, also lower than the critical values.

P-Value:
Both daily (3.80e-06) and monthly (8.02e-05) p-values are significantly less than 0.05.

My interpretation:

Both daily and monthly sales data are stationary, meaning the mean and variance are stable over time. This is a prerequisite for ARIMA modeling.

#### SARIMAX Model Summary
The SARIMAX summary provides information about the ARIMA model (ARIMA(1, 0, 1)):

Coefficients:

ar.L1: The coefficient for the AR(1) term is 0.6870, indicating a strong positive relationship with the immediate prior value.
ma.L1: The coefficient for the MA(1) term is -0.3431, indicating a moderate inverse relationship with the immediate error term.

P-Values:

The p-value for ar.L1 (0.015) is less than 0.05, making it statistically significant.
The p-value for ma.L1 (0.339) is greater than 0.05, so it is not statistically significant.
AIC and BIC:

AIC (1108.341) and BIC (1115.825) are measures of model quality. Lower values indicate better model fit.

### AWS QuickSight Dashboard:

<img width="2028" alt="Xnapper-2024-12-19-22 52 08" src="https://github.com/user-attachments/assets/2175ab22-a892-4fb1-91a3-e3a324f3439d" />
<img width="2028" alt="Xnapper-2024-12-19-22 52 54" src="https://github.com/user-attachments/assets/78eeaf65-33ed-4c25-9270-03d40143f762" />
<img width="2028" alt="Xnapper-2024-12-19-22 53 35" src="https://github.com/user-attachments/assets/1537adbb-038e-4fd9-83d3-f7d5913347d1" />
<img width="1720" alt="Xnapper-2024-12-19-23 16 20" src="https://github.com/user-attachments/assets/53d0b701-f395-4976-a307-ce359eaeea3c" />

### Final dashboard overview and individual chart insights:

1. Sales Performance by Region:

This bar chart compares total sales across regions (West, East, Central, South). The West region leads with the highest sales, followed by the East. This suggests a strong customer base or better distribution channels in the West. In contrast, the South region lags behind, indicating a need for strategic focus to improve sales there.

2. Sales Trends Over Time:

This line chart tracks sales over time, displaying seasonal peaks and overall growth trends. The periodic spikes may align with holidays, promotions, or other key events. The increasing trend reflects business growth, but further investigation is needed to address any dips or inconsistencies.

3. Forecasted Sales:

This plot predicts future sales based on historical data. The projected downward trend in sales indicates a potential slowdown, possibly due to seasonal patterns or market saturation. This forecast allows the business to plan marketing strategies or operational adjustments to counteract the decline.

4. Discount Impact on Sales:

The scatter plot illustrates the relationship between discounts and sales volume. While higher discounts seem to drive sales, there is a diminishing return effect after a certain point. Strategic discounting can boost sales without eroding profit margins.

5. High-Value Customers:

The table lists top customers by sales, identifying the most valuable accounts. Sean Miller, for example, contributes significantly to revenue. These insights can guide customer retention strategies, like personalized offers or loyalty programs, to maintain and grow these relationships.

6. Profitability by Product Category:

This pie chart breaks down sales and profitability by product category. Segments like Consumer and Corporate dominate sales, but Home Office has a smaller share. This view can help target underperforming categories or reinforce high-margin areas.

7. Product Performance:

The bubble chart compares product categories by sales and quantity sold. For example, Technology products may generate high revenue but lower quantities, suggesting premium pricing. Furniture, with moderate sales and quantities, offers opportunities for growth by optimizing pricing or inventory.

8. Shipping Mode Analysis:

This bar chart compares sales and quantities across shipping modes. Standard Class handles the highest volume, indicating customer preference or cost efficiency. Same Day may account for fewer sales but cater to urgent customer needs, justifying its premium pricing.

9. Profit Margin Analysis:

The KPI visual highlights the profit margin for Technology (17.4%) and Office Supplies (17.04%, up by 2.12%). These figures help assess financial health, showing where profitability is growing or needs improvement.

10. Geographical Insights:
The map visual provides a geographic view of sales performance. Major cities like New York and Los Angeles appear as hotspots, highlighting markets with the highest sales. This insight supports decisions on resource allocation or regional marketing.
---
## Results

### **Key Insights**
1. **Sales Trends**:
   - Monthly sales show a cyclical pattern with an overall upward trend over the years.
   - Daily sales exhibit high volatility with occasional spikes due to promotional events or bulk purchases.

2. **Forecasting**:
   - The ARIMA model captured historical trends effectively, with forecasted values aligning with the cyclical nature of sales data.
   - The forecast suggests continued growth, with seasonal dips and rises.

3. **Model Performance**:
   - The ARIMA model provided reasonable predictions with an MAE of 18,962 and RMSE of 24,280, suggesting it captured overall patterns well.

---

## Project Structure

```
sales-forecasting-project/
├── data/                # Datasets used in the project
├── notebooks/           # Jupyter notebooks for analysis
│   └── sales_forecasting_project.ipynb
├── images/              # Screenshots and visualizations
├── requirements.txt     # Dependencies for the project
├── .gitignore           # Ignored files
├── README.md            # Project overview
```

---

## How to Run the Project

### **Prerequisites**
- Python 3.8+
- PostgreSQL database credentials (host, user, password, database name).
- AWS account for accessing Quicksight and RDS.

### **Steps**
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/sales-forecasting-project.git
   cd sales-forecasting-project
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables:
   ```bash
   export DB_PASSWORD="your_password_here"
   ```

4. Run the Jupyter notebook:
   ```bash
   jupyter notebook notebooks/sales_forecasting_project.ipynb
   ```

---

## Future Work
- Experiment with SARIMA models to capture seasonality explicitly.
- Integrate external factors like holidays, promotions, or marketing campaigns to improve forecasting accuracy.
- Explore deep learning techniques like LSTMs for time series forecasting.
- Expand the project to include product-level sales forecasts.

---

I would hope my project demonstrates a comprehensive integration of Cloud Technologies, Data Engineering, Data Visualisation, and Machine Learning, showcasing a full-stack approach to solving real-world business problems!


