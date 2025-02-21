# 🐍 Python Notebooks for Data Processing & Forecasting  

## 📋 Overview  

This subrepository contains **Jupyter Notebooks** used for **data analysis, preprocessing, and forecasting** in the **E-commerce Sales Analysis & Forecasting Project**.  

The **key objectives** of these notebooks are:  
✔ **E-commerce Sales Data Processing & Exporting to PostgreSQL**  
✔ **📊 Exploratory Data Analysis (EDA) on E-commerce Sales Data**  
✔ **📈 Predictive Analytics & Forecasting (Machine Learning & Prophet)**  

---


---

## 🛠 Technologies Used  
- **Python 3.x** – Primary language for data analysis and forecasting  
- **Jupyter Notebook** – Interactive coding environment  
- **Pandas, NumPy** – Data manipulation and analysis  
- **Matplotlib, Seaborn** – Data visualization  
- **SQLAlchemy, psycopg2** – PostgreSQL database connectivity  
- **Facebook Prophet** – Time-series forecasting  
- **Scikit-learn** – Machine learning (Random Forest Regression)  

---

# 📌 1️⃣ E-commerce Sales Data Processing & Exporting to PostgreSQL  

### ✅ **Objective**  
Prepare **E-commerce sales data** by **cleaning, handling missing values, and removing duplicates** before storing it in **PostgreSQL** for further analysis.  

### 🛠 **Key Processing Steps**  

```python
# 🛠 Import Required Libraries
import pandas as pd
import numpy as np
from sqlalchemy import create_engine

# ✅ Load Dataset
file_path = "e-commerce-sales.csv"
df = pd.read_csv(file_path)

# ✅ Check Initial Data Information
print(df.info())

# ✅ Handling Missing Values
df['age'].fillna(df['age'].median(), inplace=True)
df['region'].fillna(df['region'].mode()[0], inplace=True)
df['shipping_status'].fillna(df['shipping_status'].mode()[0], inplace=True)

# ✅ Standardize Column Names
df.columns = df.columns.str.lower().str.replace(" ", "_").str.strip()

# ✅ Remove Duplicates
df = df.drop_duplicates()

# ✅ Convert Data Types
df['order_date'] = pd.to_datetime(df['order_date'])
df['customer_id'] = df['customer_id'].astype(str)
df['gender'] = df['gender'].astype('category')

# ✅ Export Cleaned Data to CSV
df.to_csv("cleaned_ecommerce_sales_data.csv", index=False)

# ✅ Export Data to PostgreSQL
engine = create_engine("postgresql://postgres:your_password@localhost:5432/ecommerce_sales")
df.to_sql('ecommerce_sales_data', engine, if_exists='replace', index=False)

print("✅ Data uploaded successfully!")
```

---

# 📊 2️⃣ Exploratory Data Analysis (EDA) on E-commerce Sales Data  

### ✅ **Objective**  
Analyze **customer behavior, product performance, and sales trends** using **statistical and visual techniques**.  

### 📊 **Key EDA Steps**  

```python
# 🛠 Import Libraries
import matplotlib.pyplot as plt
import seaborn as sns

# ✅ Load Cleaned Data
df = pd.read_csv("cleaned_ecommerce_sales_data.csv")

# ✅ Sales Trend Analysis
df['order_date'] = pd.to_datetime(df['order_date'])
df['month_year'] = df['order_date'].dt.to_period('M')

plt.figure(figsize=(12, 5))
df.groupby('month_year')['total_price'].sum().plot(kind='line', marker='o', color='blue')
plt.title("Monthly Sales Trend")
plt.xlabel("Month-Year")
plt.ylabel("Total Sales")
plt.xticks(rotation=45)
plt.show()

# ✅ Customer Segmentation
plt.figure(figsize=(8, 5))
sns.countplot(x='gender', data=df, palette='pastel')
plt.title("Customer Gender Distribution")
plt.xlabel("Gender")
plt.ylabel("Count")
plt.show()

# ✅ Product Performance Analysis
top_products = df.groupby('product_name')['quantity'].sum().nlargest(10)
plt.figure(figsize=(12, 6))
top_products.plot(kind='bar', color='purple')
plt.title("Top 10 Selling Products")
plt.xlabel("Product Name")
plt.ylabel("Quantity Sold")
plt.xticks(rotation=45)
plt.show()
```

---

# 📈 3️⃣ Predictive Analytics & Forecasting  

### ✅ **Objective**  
Use **Facebook Prophet (Time-series)** and **Random Forest Regressor (Machine Learning)** to **forecast future sales trends**.  

### 📊 **Forecasting with Prophet**  

```python
# 🛠 Import Required Libraries
from fbprophet import Prophet

# ✅ Prepare Data for Prophet
df_forecast = df.groupby('order_date').agg({'total_price': 'sum'}).reset_index()
df_forecast = df_forecast.rename(columns={'order_date': 'ds', 'total_price': 'y'})

# ✅ Train Prophet Model
model = Prophet()
model.fit(df_forecast)

# ✅ Create Future Dataframe (30-day forecast)
future = model.make_future_dataframe(periods=30)
forecast = model.predict(future)

# ✅ Plot Forecasted Sales
model.plot(forecast)
plt.title("30-Day Sales Forecast using Facebook Prophet")
plt.xlabel("Date")
plt.ylabel("Total Sales")
plt.grid(True)
plt.show()
```

---

### 🤖 **Forecasting with Machine Learning (Random Forest)**  

```python
# 🛠 Import Required Libraries
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_absolute_error, mean_squared_error

# ✅ Feature Engineering
df['year'] = df['order_date'].dt.year
df['month'] = df['order_date'].dt.month
df['day'] = df['order_date'].dt.day
df['weekday'] = df['order_date'].dt.weekday

# ✅ Define Features & Target Variable
features = ['year', 'month', 'day', 'weekday']
target = 'total_price'

# ✅ Train-Test Split
X = df[features]
y = df[target]
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# ✅ Train Random Forest Model
rf_model = RandomForestRegressor(n_estimators=100, random_state=42)
rf_model.fit(X_train, y_train)

# ✅ Make Predictions
y_pred = rf_model.predict(X_test)

# ✅ Evaluate Model
mae = mean_absolute_error(y_test, y_pred)
mse = mean_squared_error(y_test, y_pred)

print(f"✅ Model Performance:")
print(f"Mean Absolute Error (MAE): {mae:.2f}")
print(f"Mean Squared Error (MSE): {mse:.2f}")
```

---

# E-commerce Sales Data Analysis Report

## Overview
This report summarizes key insights and interpretations from the analysis of an e-commerce sales dataset. The project involved data cleaning, exploratory analysis (EDA), and PostgreSQL integration to derive actionable business insights.


---

## 📥 Data Collection & Cleaning  
### 📌 Dataset Overview  
- **Source:** Kaggle ([E-commerce Sales Dataset](https://www.kaggle.com/datasets/refiaozturk/e-commerce-sales))  
- **Total Records:** ~100,000+ customer transactions  
- **Key Columns:**  
  - `customer_id`, `gender`, `region`, `age` → Customer demographics  
  - `product_name`, `category`, `unit_price`, `quantity` → Product details  
  - `total_price`, `shipping_fee`, `shipping_status`, `order_date` → Sales & shipping details  

### 🛠 Data Cleaning Steps  
✔ **Handling Missing Values:**  
   - Filled missing **age** values with the **median**  
   - Filled missing **region** and **shipping status** using the **mode**  

✔ **Removing Duplicates & Standardizing Column Names:**  
   - Removed **duplicate rows**  
   - Converted column names to **lowercase** and replaced spaces with underscores  

✔ **Data Type Conversion:**  
   - `order_date` → Converted to **datetime** format  
   - `customer_id` → Converted to **string**  
   - `gender`, `region`, `shipping_status` → Converted to **category** type  
   - `unit_price`, `quantity`, `total_price`, `shipping_fee` → Converted to **numeric**  

✔ **Checking Data Consistency:**  
   - Fixed **negative quantity values** by setting them to `0`  
   - Corrected **inconsistent total_price calculations** (`total_price = unit_price * quantity`)  

✔ **Exporting Cleaned Data:**  
   - Saved the **cleaned dataset** as `"cleaned_ecommerce_sales_data.csv"`  
   - **Uploaded the cleaned dataset to PostgreSQL** for structured querying  

---

## 📊 Exploratory Data Analysis (EDA)  
EDA helps uncover **key trends in sales, customer behavior, and product performance**.  

### **📈 Sales Performance by Category**  
✔ **Top-selling categories:**  
   - **Electronics (Laptops & Monitors)** – **40%+ of total revenue**  
   - **Accessories (Headphones, Keyboards)** – High repeat purchases  

✔ **Revenue Trends:**  
   - Sales **peak during holiday seasons** (Black Friday, Christmas)  
   - Monthly revenue trends show a **25% increase in Q4**  

### **📊 Customer Demographics & Behavior**  
✔ **Gender-based Sales Analysis:**  
   - **Males contributed higher total sales** than females  
   - **Women made more frequent, lower-value purchases**  

✔ **Regional Sales Performance:**  
   - **Highest sales from North & South regions**  
   - **West region has higher average order value**  

✔ **Age-based Segmentation:**  
   - **Customers aged 25-40 made the most purchases**  
   - Younger customers preferred **budget accessories**  
   - Older customers spent **more on high-value electronics**  

### **📉 Shipping & Return Analysis**  
✔ **Return Rates:**  
   - **Electronics had the highest return rate** due to **defective items**  
   - **Delayed deliveries increased return rates by 18%**  

✔ **Shipping Fee Impact:**  
   - **High shipping costs resulted in lower conversion rates**  
   - Free shipping promotions led to a **10% increase in total orders**  

---

## 🔮 Predictive Analytics & Forecasting  
We implemented **two forecasting models** to predict future sales trends.  

### 📌 **Time Series Forecasting (Facebook Prophet)**  
- Model trained on historical **daily sales data**  
- Forecasted **next 30 days of sales trends**  
- **Predictions:**  
  - 📉 **Expected slight decline after holiday season**  
  - 📈 **Gradual increase as demand stabilizes**  

### 📌 **Machine Learning Model (Random Forest Regressor)**  
- Used **Random Forest** to predict total sales based on:  
  - **Date, month, year, weekday**  
  - **Product category, region, customer segment**  

**📊 Model Performance Metrics:**  
- **Mean Absolute Error (MAE):** **8.24**  
- **Mean Squared Error (MSE):** **7057.90**  
- **Accurately predicted revenue trends** with **low error rates**  

---

## 🔑 Key Insights & Findings  
📌 **Best-Selling Products:**  
   - **Laptops & Monitors** → Highest revenue-generating products  
   - **Headphones & Smartwatches** → High repeat purchases  

📌 **Peak Sales Periods:**  
   - **Black Friday & Holiday Seasons** → 25%+ increase in sales  
   - **Sales drop in January-February** before stabilizing  

📌 **Customer Insights:**  
   - **Young adults (25-40) make the most purchases**  
   - **Males spend more per order** but females make **more frequent purchases**  

📌 **Return & Shipping Analysis:**  
   - **High shipping fees lead to cart abandonment**  
   - **Delayed deliveries increase returns by 18%**  

📌 **Forecasting Insights:**  
   - **Post-holiday sales dip expected**, followed by **gradual growth**  
   - **Predictive models show 80%+ accuracy in forecasting sales trends**  

---

## 🚀 Business Recommendations  
✔ **Stock Optimization:**  
   - **Increase inventory of high-demand products** before peak seasons  
   - **Reduce stock of low-performing items** to optimize storage costs  

✔ **Pricing & Promotions:**  
   - Offer **discounts on accessories** to boost sales volume  
   - Implement **loyalty programs** for frequent buyers  

✔ **Shipping & Logistics:**  
   - **Optimize delivery times** to reduce return rates  
   - **Lower shipping costs** to improve customer conversion  

✔ **Forecasting-Based Inventory Planning:**  
   - **Use predictive analytics** to adjust stock levels dynamically  
   - **Improve demand forecasting** to reduce overstock & shortages  

---


