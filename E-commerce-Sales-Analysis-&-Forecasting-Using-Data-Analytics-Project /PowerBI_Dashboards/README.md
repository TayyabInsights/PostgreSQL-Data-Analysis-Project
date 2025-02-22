# **E-Commerce Sales Dashboard**

## **Overview**
This repository contains an interactive **Power BI dashboard** designed to analyze and visualize e-commerce sales performance. The dashboard provides insights into **sales trends, profitability, customer demographics, order distribution, and regional performance**.

![E-Commerce Sales Dashboard](https://github.com/TayyabInsights/PostgreSQL-Data-Analysis-Project/blob/main/E-commerce-Sales-Analysis-%26-Forecasting-Using-Data-Analytics-Project%20/PowerBI_Dashboards/ecommerce_sales%20Copy.pdf)

## **Dataset Description**
The dataset used for this dashboard includes the following key fields:
- **Order ID**: Unique identifier for each transaction.
- **Product Category**: Type of product purchased.
- **Total Sales**: Total revenue generated per order.
- **Total Profit**: Profit earned per order.
- **Profit Margin (%)**: Profitability ratio calculated as (Total Profit / Total Sales) * 100.
- **Order Status**: Status of the order (Delivered, In Transit, Returned).
- **Customer Age Group**: Categorized as 18-24, 25-39, 40-59, 60+.
- **Gender**: Male or Female.
- **Region**: Geographic location of the customer.
- **Order Date**: Date of purchase.

## **Dashboard Features**
### **1. KPIs (Key Performance Indicators)**
- **Total Sales**: $1.38M
- **Total Profit**: $1.37M
- **Average Order Value (AOV)**: $1.38K
- **Profit Margin**: 99.10%
- **Order Breakdown**:
  - Delivered Orders: **313 (31.3%)**
  - In Transit Orders: **379 (37.9%)**
  - Returned Orders: **308 (30.8%)**

### **2. Sales Performance by Product Category**
- **Electronics** is the top-performing category, followed by **Wearables** and **Accessories**.
- Analyzing best-selling products within each category can further improve inventory management.

### **3. Order Distribution and Shipping Status**
- A high percentage of orders (30.8%) are **returned**, which could indicate product quality issues or customer dissatisfaction.
- In Transit orders (37.9%) highlight the importance of tracking logistics efficiency.

### **4. Sales Trends Over Time**
- Monthly sales trends help identify peak months for revenue generation.
- Insights from seasonality trends can guide marketing and promotional strategies.

### **5. Customer Demographics Analysis**
- **Age Group 40-59 and 25-39 contribute the highest sales**, showing middle-aged buyers are the most active customers.
- **Gender distribution is balanced** (52.4% Male, 47.6% Female), allowing for targeted marketing efforts.

### **6. Regional Sales Performance**
- Filter options for **East, North, South, and West** enable detailed regional analysis.
- Identifying top-performing regions helps in supply chain and distribution planning.

## **Key Insights and Business Recommendations**
1. **Investigate the High Return Rate**
   - With nearly 31% of orders being **returned**, businesses should analyze the reasons (e.g., product quality, incorrect shipments, or customer dissatisfaction).
2. **Refine Target Marketing**
   - Middle-aged customers (40-59 and 25-39) are driving the majority of sales. **Personalized marketing campaigns** targeting their preferences could further boost revenue.
3. **Optimize Inventory and Logistics**
   - **Monthly sales trends** should be used to ensure proper stock levels and reduce inventory holding costs.
4. **Enhance Profitability Analysis**
   - A **99.10% profit margin** suggests a potential data inconsistency or miscalculated cost figures. The pricing and cost structure should be reviewed to ensure accuracy.

## **Dashboard Creation Process**
### **1. Data Cleaning and Transformation (Power Query)**
- Removed duplicates and missing values.
- Standardized date format and categorical data.
- Calculated new columns for **Profit Margin (%)** and **AOV (Total Sales / Total Orders)**.

### **2. DAX Measures for Key Metrics**
```DAX
Total Sales = SUM(SalesData[Total Sales])
Total Profit = SUM(SalesData[Total Profit])
Profit Margin (%) = DIVIDE([Total Profit], [Total Sales], 0) * 100
AOV = DIVIDE(SUM(SalesData[Total Sales]), [Total Orders], 0)
```

### **3. Visualization Design in Power BI**
- **KPI Cards** for Total Sales, Total Profit, AOV, and Profit Margin.
- **Clustered Column Chart** for Sales Trends over Time.
- **Pie Chart** for Order Status Breakdown.
- **Bar Chart** for Product Category Sales Performance.
- **Slicer Filters** for Age Group, Region, and Gender.

## **How to Use the Dashboard**
1. **Download the Power BI file (.pbix) from this repository**.
2. **Open the file in Power BI Desktop**.
3. **Use the slicers to filter data by region, age group, gender, or order status**.
4. **Analyze sales trends, customer demographics, and order performance**.

## **Future Enhancements**
- **Integration with Real-Time Data** to update metrics dynamically.
- **Customer Segmentation Analysis** for better targeting and personalization.
- **Advanced Predictive Analytics** to forecast future sales trends.

## **Conclusion**
This Power BI dashboard provides a **comprehensive analysis** of e-commerce sales, highlighting key insights related to **profitability, customer demographics, and sales performance**. By leveraging these insights, businesses can **optimize marketing strategies, improve operational efficiency, and enhance customer experience**.

---
### **📌 Author**
👤 **Tayyab**  
🚀 **Data Analytics & Power BI Specialist**  
📧 Contact: [LinkedIn Profile](#)  
