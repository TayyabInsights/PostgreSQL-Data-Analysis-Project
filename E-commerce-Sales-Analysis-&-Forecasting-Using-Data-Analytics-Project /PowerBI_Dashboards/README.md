# **📊 E-Commerce Sales Power BI Dashboard**

## **📌 Overview**
This repository contains an interactive **Power BI dashboard** designed to analyze and visualize **e-commerce sales performance**. The dashboard provides insights into:
✅ **Sales Trends**  
✅ **Profitability**  
✅ **Customer Demographics**  
✅ **Order Distribution**  
✅ **Regional Performance**  

📌 **Live Dashboard Preview:**  
![E-Commerce Sales Dashboard](https://github.com/TayyabInsights/PostgreSQL-Data-Analysis-Project/blob/main/E-commerce-Sales-Analysis-%26-Forecasting-Using-Data-Analytics-Project%20/PowerBI_Dashboards/ecommerce_sales%20Copy.pdf)

---

## **📂 Dataset Description**
The dataset used for this dashboard includes the following key fields:
- **🆔 Order ID** – Unique identifier for each transaction.
- **📦 Product Category** – Type of product purchased.
- **💰 Total Sales** – Total revenue generated per order.
- **📈 Total Profit** – Profit earned per order.
- **📊 Profit Margin (%)** – (Total Profit / Total Sales) * 100.
- **🚚 Order Status** – Delivered, In Transit, Returned.
- **👥 Customer Age Group** – Categorized as **18-24, 25-39, 40-59, 60+**.
- **🧑‍🤝‍🧑 Gender** – Male or Female.
- **🌍 Region** – Geographic location of the customer.
- **📅 Order Date** – Date of purchase.

---

## **📊 Dashboard Features**
### **1️⃣ Key Performance Indicators (KPIs)**
- **🛒 Total Sales**: **$1.38M**
- **💵 Total Profit**: **$1.37M**
- **📉 Average Order Value (AOV)**: **$1.38K**
- **📊 Profit Margin**: **99.10%**
- **🚚 Order Breakdown:**
  - ✅ Delivered Orders: **313 (31.3%)**
  - 📦 In Transit Orders: **379 (37.9%)**
  - ❌ Returned Orders: **308 (30.8%)**

### **2️⃣ Sales Performance by Product Category**
- **📡 Electronics** is the **top-performing** category, followed by **Wearables** and **Accessories**.
- **📦 Best-selling products** analysis helps in **inventory management**.

### **3️⃣ Order Distribution and Shipping Status**
- A **high return rate (30.8%)** suggests product quality issues or customer dissatisfaction.
- **Logistics efficiency** insights through in-transit orders (37.9%).

### **4️⃣ Sales Trends Over Time**
- **📊 Monthly trends** help identify peak revenue periods.
- **📅 Seasonality trends** guide marketing strategies.

### **5️⃣ Customer Demographics Analysis**
- **👥 Age Groups 40-59 and 25-39 contribute the highest sales**.
- **🧑‍🤝‍🧑 Gender distribution** is balanced (52.4% Male, 47.6% Female).

### **6️⃣ Regional Sales Performance**
- **🌍 Regional filters** for **East, North, South, and West** enable detailed analysis.
- **🏆 Top-performing regions** optimize supply chain and distribution.

---

## **📌 Key Insights & Business Recommendations**
1. **🔍 Investigate the High Return Rate**
   - Analyze **customer feedback, product quality, and return reasons**.
2. **🎯 Target Marketing Optimization**
   - **Middle-aged buyers (40-59 & 25-39) drive most sales**, optimize campaigns accordingly.
3. **📦 Inventory & Logistics Management**
   - Use **monthly sales trends** to manage **stock levels** efficiently.
4. **💡 Profitability Review**
   - **99.10% profit margin** indicates possible **data inconsistencies** – review pricing structures.

---

## **🛠 Dashboard Creation Process**

### **1️⃣ Data Cleaning and Transformation (Power Query)**
- ✅ Removed duplicates and missing values.
- ✅ Standardized **date formats** and **categorical data**.
- ✅ Created new columns for **Profit Margin (%)** and **AOV** *(Total Sales / Total Orders)*.

### **2️⃣ DAX Measures for Key Metrics**
```DAX
Total Sales = SUM(SalesData[Total Sales])
Total Profit = SUM(SalesData[Total Profit])
Profit Margin (%) = DIVIDE([Total Profit], [Total Sales], 0) * 100
AOV = DIVIDE(SUM(SalesData[Total Sales]), [Total Orders], 0)
```

### **3️⃣ Columns & Measures Created in Power BI**
| **Measure Name**           | **Formula Used**  | **Purpose** |
|---------------------------|-----------------|-------------|
| **Total Sales**          | SUM(SalesData[Total Sales]) | Calculates total revenue |
| **Total Profit**         | SUM(SalesData[Total Profit]) | Determines total earnings |
| **Profit Margin (%)**    | DIVIDE([Total Profit], [Total Sales], 0) * 100 | Analyzes profitability ratio |
| **AOV (Average Order Value)** | DIVIDE(SUM(SalesData[Total Sales]), [Total Orders], 0) | Computes revenue per order |
| **Total Orders**         | DISTINCTCOUNT(SalesData[Order ID]) | Tracks unique orders |
| **Return Rate**          | DIVIDE([Returned Orders], [Total Orders], 0) * 100 | Monitors returns percentage |

### **4️⃣ Visualization Design in Power BI**
- 📌 **KPI Cards** – Display key metrics **(Total Sales, Total Profit, AOV, Profit Margin)**.
- 📊 **Clustered Column Chart** – Sales Trends over Time.
- 🍕 **Pie Chart** – Order Status Breakdown.
- 📊 **Bar Chart** – Product Category Performance.
- 🎛 **Slicer Filters** – **Age Group, Region, Gender**.

---

## **🚀 Future Enhancements**
📌 **Real-time Data Integration** – Update dashboard dynamically.  
📌 **Customer Segmentation Analysis** – Improve personalization.  
📌 **Advanced Predictive Analytics** – Forecast future sales trends.  

---

## **📢 Conclusion**
This **Power BI dashboard** provides a **comprehensive analysis** of e-commerce sales, offering key insights into **profitability, customer demographics, and sales performance**. By leveraging these insights, businesses can:
✅ **Optimize marketing strategies**  
✅ **Improve operational efficiency**  
✅ **Enhance customer experience**  

📌 **Star this repository ⭐ and follow for more insights!**
