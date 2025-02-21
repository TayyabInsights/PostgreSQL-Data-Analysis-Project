# 📊 E-commerce Sales Analysis & Forecasting Using Data Analytics  

## 📑 Table of Contents
- [Project Overview](#project-overview)
- [Project Diagram](#project-diagram)
- [Problem Statement](#problem-statement)
- [Methodology](#methodology)
- [Technologies Used](#technologies-used)
- [Folder Structure](#folder-structure)
- [How to Use the Project](#how-to-use-the-project)
- [Data Collection](#data-collection)
- [Data Preparation](#data-preparation)
- [Dashboard Overview](#dashboard-overview)
- [Key Findings](#key-findings)
- [Limitations](#limitations)
- [Conclusion and Recommendations](#conclusion-and-recommendations)
- [Let’s Connect!](#lets-connect)

## 📋 Project Overview  <a id="project-overview"></a>
This project analyzes **E-commerce sales trends, customer purchasing behavior, and product performance** using **PostgreSQL, Python, and Power BI**. The objective is to extract key insights and **forecast future sales trends** to help businesses improve **decision-making, inventory management, and revenue optimization**.  

## 📌 Project Diagram  <a id="project-diagram"></a>
![Project Diagram](https://github.com/TayyabInsights/PostgreSQL-Data-Analysis-Project/blob/main/E-commerce-Sales-Analysis-%26-Forecasting-Using-Data-Analytics-Project/Images/diagram.png)

## ❓ Problem Statement  <a id="problem-statement"></a>
How can E-commerce businesses identify top-performing products, high-value customers, and seasonal trends? How can sales be forecasted to optimize inventory management and marketing strategies?

## 🛠 Methodology  <a id="methodology"></a>
### 1️⃣ Data Collection & Preprocessing  
📌 **Extracted raw data from Kaggle and stored it in PostgreSQL** for structured analysis.  
📌 **Performed data cleaning in Python:**  
   ✔ Converted column names to lowercase  
   ✔ Removed duplicates and handled missing values  
   ✔ Standardized data types (date, currency, numeric values)  

### 2️⃣ Exploratory Data Analysis (EDA) in Python  
📌 **Analyzed trends in customer behavior, sales performance, and product categories**.  
📌 **Created visualizations** using **Matplotlib and Seaborn** to identify insights.  

### 3️⃣ Sales Forecasting (Machine Learning Models)  
📌 Used **Facebook Prophet for time-series forecasting** to predict future sales.  
📌 Trained a **Random Forest model** to analyze factors influencing revenue growth.  
📌 Evaluated model performance using **Mean Absolute Error (MAE) and Mean Squared Error (MSE)**.  

### 4️⃣ Interactive Dashboard in Power BI  
📌 **Designed a professional Power BI dashboard** to visualize key insights:  
✔ **Total Revenue & Profit Trends**  
✔ **Top-Selling Products & Categories**  
✔ **Monthly Sales & Customer Segmentation**  
✔ **Shipping Delays Impact on Customer Churn**  

## 💻 Technologies Used  <a id="technologies-used"></a>
- **PostgreSQL:** Database storage, SQL queries for analysis  
- **Python:** Data cleaning, EDA, ML forecasting models  
- **Power BI:** Interactive dashboard and visualizations  

## 📂 Folder Structure  <a id="folder-structure"></a>
```
E-commerce-Sales-Analysis/
│── 📄 About-Me/                 # Author's background
│── 📄 SQL_Scripts/              # SQL queries for data processing
│   ├── data_cleaning.sql
│   ├── data_extraction.sql
│── 📄 Python_Notebooks/         # Jupyter Notebooks for analysis
│   ├── EDA.ipynb
│   ├── forecasting_models.ipynb
│── 📄 PowerBI_Dashboards/       # Power BI dashboard file
│   ├── E-commerce_Sales_Dashboard.pbix
│── 📄 project_presentation/     # Presentation file
│   ├── project_presentation.pdf
│── 🖼️ Images/                    # Screenshots & visuals
│── 📝 README.md                  # Main project documentation
```

## 📝 How to Use the Project  <a id="how-to-use-the-project"></a>
1. Run the SQL scripts to set up the database in PostgreSQL.
2. Open Python notebooks for EDA and forecasting analysis.
3. View the interactive dashboard in Power BI.

## 📊 Data Collection  <a id="data-collection"></a>
### 📊 Dataset Name: [E-commerce Sales and Customer Insights Dataset](https://www.kaggle.com/datasets/refiaozturk/e-commerce-sales)  
📌 **Source:** Kaggle  
📌 **Size:** ~100,000+ customer transactions  
📌 **Time Period:** Multiple years of E-commerce sales  

### 📝 Key Columns in the Dataset:  
- **customer_id:** Unique identifier for each customer  
- **gender:** Male or Female classification for demographic analysis  
- **region:** Geographical region of the customer  
- **age:** Customer age, useful for segmentation  
- **product_name:** Product purchased by the customer  
- **category:** Product category (e.g., Electronics, Accessories, etc.)  
- **unit_price:** Price per unit of product  
- **quantity:** Number of units purchased  
- **total_price:** Total cost paid per order  
- **shipping_fee:** Cost of shipping for the order  
- **shipping_status:** Order status (e.g., Delivered, Returned, In Transit)  
- **order_date:** Date the order was placed  

## 🧹 Data Preparation  <a id="data-preparation"></a>
📌 **Extracted raw data from Kaggle and stored it in PostgreSQL** for structured analysis.  
📌 **Performed data cleaning in Python:**  
✔ Converted column names to lowercase  
✔ Removed duplicates and handled missing values  
✔ Standardized data types (date, currency, numeric values)  

## 📈 Dashboard Overview  <a id="dashboard-overview"></a>
### 👀 What’s Inside the Dashboard?  
✔ **📌 Total Sales Overview** (KPI Indicators)  
✔ **📊 Best-Selling Products & Customer Segments**  
✔ **📈 Monthly Sales Trend Analysis**  
✔ **🚚 Impact of Shipping Status on Customer Satisfaction**  
✔ **🔮 Sales Forecasting (Next 30 Days)**  

## 🔑 Key Findings  <a id="key-findings"></a>
📌 **Most Profitable Products:** Laptops and Monitors contribute over 40% of total revenue.  
📌 **Peak Sales Months:** November & December due to holiday shopping.  
📌 **Customer Behavior Insights:** Loyal customers generate 60% of sales revenue.  
📌 **Shipping Impact:** Delays increase refund rates by 25%.  

## ⚠ Limitations  <a id="limitations"></a>
📌 Dataset may not reflect real-time trends.  
📌 Assumptions made in forecasting models may affect accuracy.  

## 🎯 Conclusion and Recommendations  <a id="conclusion-and-recommendations"></a>
✔ Improve stock availability for high-demand products.  
✔ Enhance targeted marketing for returning customers.  
✔ Optimize logistics to reduce shipping delays.  
✔ Implement AI-driven demand forecasting for inventory management.  

## 🔗 Let’s Connect!  <a id="lets-connect"></a>
💼 [LinkedIn](https://www.linkedin.com/in/your-profile)  
📧 [Email](mailto:your-email@example.com)  
🌐 [Portfolio](https://your-portfolio.com)  
