# 📌 SQL Scripts for Data Processing  


---

## 📋 Overview  

In this part of the project, I will be mentioning the **details of the SQL queries** used for data processing and analysis in **pgAdmin 4**. These queries help in **data extraction, transformation, and exploratory analysis** of e-commerce sales data stored in **PostgreSQL**.  

The key objectives of these queries are:  
✔ Cleaning and preparing the data  
✔ Extracting business insights  
✔ Identifying customer purchasing trends  
✔ Analyzing product and sales performance  
✔ Evaluating shipping and return patterns  

---

## 🛠 Database Used  

- **Database Name:** `ecommerce_sales_data`  
- **Tool Used:** **PostgreSQL (pgAdmin 4)**  
- **Table Name:** `ecommerce_sales_data`  

---

## 📝 SQL Queries  

### 1️⃣ **Check Initial Data**  

#### **Check the first 10 rows of the dataset**  
```sql
SELECT * FROM ecommerce_sales_data LIMIT 10;
```

#### **Check distinct values in the 'region' column**  
```sql
SELECT DISTINCT region FROM ecommerce_sales_data;
```

#### **Count unique customers**  
```sql
SELECT COUNT(DISTINCT customer_id) AS unique_customers 
FROM ecommerce_sales_data;
```

---

### 2️⃣ **Exploratory Data Analysis (EDA)**  

#### **Check Sales Performance by Category**  
```sql
SELECT category, SUM(total_price) AS total_sales
FROM ecommerce_sales_data
GROUP BY category
ORDER BY total_sales DESC;
```

#### **Check how many purchases each customer made**  
```sql
SELECT customer_id, COUNT(*) AS purchase_count
FROM ecommerce_sales_data
GROUP BY customer_id
ORDER BY purchase_count DESC;
```

#### **Calculate the Average Order Value (AOV)**  
```sql
SELECT AVG(total_price) AS average_order_value 
FROM ecommerce_sales_data;
```

---

### 3️⃣ **Sales Performance Analysis**  

#### **Analyze Sales Performance by Gender**  
```sql
SELECT gender, SUM(total_price) AS total_sales
FROM ecommerce_sales_data
GROUP BY gender
ORDER BY total_sales DESC;
```

#### **Analyze Total Sales by Category**  
```sql
SELECT category, COUNT(*) AS number_of_sales, SUM(total_price) AS total_sales
FROM ecommerce_sales_data
GROUP BY category
ORDER BY total_sales DESC;
```

#### **Analyze the Relationship Between Quantity Sold and Total Sales**  
```sql
SELECT quantity, SUM(total_price) AS total_sales
FROM ecommerce_sales_data
GROUP BY quantity
ORDER BY quantity;
```

---

### 4️⃣ **Customer Insights**  

#### **Find the Top Customers with the Highest Purchases**  
```sql
SELECT customer_id, SUM(total_price) AS total_spent
FROM ecommerce_sales_data
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 10;
```

#### **Identify the Most Frequent Customers**  
```sql
SELECT customer_id, COUNT(*) AS total_orders
FROM ecommerce_sales_data
GROUP BY customer_id
ORDER BY total_orders DESC
LIMIT 10;
```

---

### 5️⃣ **Product Performance**  

#### **Find the Top 10 Products by Total Sales**  
```sql
SELECT product_name, SUM(total_price) AS total_sales
FROM ecommerce_sales_data
GROUP BY product_name
ORDER BY total_sales DESC
LIMIT 10;
```

#### **Analyze Return Rates by Product**  
```sql
SELECT product_name, COUNT(*) AS return_count
FROM ecommerce_sales_data
WHERE shipping_status = 'Returned'
GROUP BY product_name
ORDER BY return_count DESC;
```

---

### 6️⃣ **Shipping & Return Analysis**  

#### **Analyze Sales Based on Shipping Fee**  
```sql
SELECT shipping_fee, SUM(total_price) AS total_sales
FROM ecommerce_sales_data
GROUP BY shipping_fee
ORDER BY shipping_fee;
```

#### **Identify the Most Common Shipping Status**  
```sql
SELECT shipping_status, COUNT(*) AS total_orders
FROM ecommerce_sales_data
GROUP BY shipping_status
ORDER BY total_orders DESC;
```

#### **Compare Average Shipping Fee by Region**  
```sql
SELECT region, AVG(shipping_fee) AS avg_shipping_fee
FROM ecommerce_sales_data
GROUP BY region
ORDER BY avg_shipping_fee DESC;
```

---

## 🚀 Conclusion  

These SQL queries provide valuable insights into e-commerce sales data by analyzing sales performance, customer behavior, product trends, and shipping efficiency. They are essential for understanding business performance, improving marketing strategies, and optimizing inventory management.
