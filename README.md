# 🚀 Blinkit Quick-Commerce Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-CC292B?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-Data_Analytics-blue?style=for-the-badge)

An end-to-end, multi-page Power BI business intelligence solution designed to analyze order fulfillment logistics, sales seasonality, stock turnover, customer retention, and marketing efficiency for Blinkit, a leading quick-commerce platform.

This project transforms high-volume operational data into interactive, actionable visual insights using SQL, Power Query (M), and advanced DAX modeling.

---

## 📌 Table of Contents
- Executive Summary
- Dashboard Architecture
- Technical Stack
- Data Pipeline & Modeling
- Calculated Measures (DAX Snippets)
- Page-by-Page Visual Analysis
- Business Impact & Recommendations
- Repository Structure
- Setup & Installation
- Author & Contact

---

## 📊 Executive Summary

In quick-commerce platforms like Blinkit, operating at minute-level SLAs requires centralized data visibility. Managing order delays, inventory stockouts, regional demand surges, and customer churn can be overwhelming without unified reporting tools.

This project delivers a 7-page interactive dashboard containing over 300+ custom visuals, providing cross-functional analytics for executive leaders, dark-store operational managers, and performance marketing teams.

### Project Scale at a Glance
* Total Pages: 7 Interactive Report Pages
* Visual Elements: 300+ (KPI Cards, Heatmaps, Trend Lines, Slicers, Tooltips)
* Data Sources: SQL Database, Structured CSV/Excel Files
* Key Analytical Domains: Order Logistics, Regional Revenue Split, Customer LTV, Inventory Turnover Ratio, Sentiment Analysis, Marketing ROI.

---

## 📐 Dashboard Architecture

The dashboard is structured into 7 dedicated modules:

├── 1. Home                👉 Interactive Navigation & Hub Page
├── 2. Overview            👉 High-Level Executive KPIs & Regional Split
├── 3. Sales Overview      👉 Monthly Sales Trends, AOV & Product Categories
├── 4. Customer            👉 Repeat Order Rates, LTV & Top Customer Rankings
├── 5. Inventory           👉 Low-Stock Heatmaps, Tiers & Turnover Ratio
├── 6. Feedbacks           👉 Sentiment Analysis & Customer Review Keywords
└── 7. Marketing           👉 Campaign ROI & Channel Acquisition Breakdown

---

## 🛠️ Technical Stack

* Business Intelligence: Power BI Desktop
* Data Warehousing & Querying: SQL, MS Excel / CSV
* ETL & Data Cleaning: Power Query (M Language)
* Data Modeling & Analytics: DAX (Data Analysis Expressions)
* UI/UX Design: Canvas backgrounds, custom visual hierarchy, dynamic page navigation

---

## 🗄️ Data Pipeline & Modeling

### 1. Data Flow Architecture

+--------------------+        +-----------------------+        +-----------------------+
| Raw SQL / CSV Data |  --->  |   Power Query (ETL)   |  --->  | Star Schema Data Model|
| (Orders, Stock)    |        | Clean, Transform, Type|        | (Fact & Dim Tables)   |
+--------------------+        +-----------------------+        +-----------------------+
                                                                           |
                                                                           v
                                                               +-----------------------+
                                                               | Power BI Visuals      |
                                                               | (300+ Visuals, DAX)   |
                                                               +-----------------------+

### 2. Star Schema Design
The model follows an optimized Star Schema to ensure high-performance DAX evaluations:
* Fact Tables: Fact_Orders, Fact_Inventory, Fact_Marketing
* Dimension Tables: Dim_Date, Dim_Customer, Dim_Product, Dim_Region
* Relationships: 1 to Many (Single-direction filtering) between Dimension and Fact tables.

---

## 🧮 Calculated Measures (DAX Snippets)

Representative DAX formulas used across the report for dynamic metrics:

### Delivery Completion Rate (%)
Delivery Completion Rate = 
DIVIDE(
    CALCULATE(COUNT(Fact_Orders[Order_ID]), Fact_Orders[Status] = "Delivered"),
    COUNT(Fact_Orders[Order_ID]),
    0
)

### Average Order Value (AOV)
Average Order Value = 
DIVIDE([Total Revenue], [Total Orders], 0)

### Inventory Turnover Ratio
Inventory Turnover Ratio = 
DIVIDE([COGS], AVERAGE(Fact_Inventory[Stock_Value]), 0)

### Customer Retention Rate (%)
Customer Retention Rate = 
DIVIDE(
    CALCULATE(DISTINCTCOUNT(Fact_Orders[Customer_ID]), Fact_Orders[Is_Repeat_Customer] = TRUE()),
    DISTINCTCOUNT(Fact_Orders[Customer_ID]),
    0
)

---

## 🖼️ Page-by-Page Visual Analysis

### 1. Home / Landing Page
Central navigation landing page linking all operational reporting pages with custom dynamic visuals.

![Home Page](./Home.png)

### 2. Overview Page
Macro-level performance summary displaying total orders, delivery completion rates, and regional revenue breakdown.

![Overview Page](./Overview.png)

### 3. Sales Overview Page
Tracks revenue performance across product categories, monthly sales seasonality, and Average Order Value (AOV) growth.

![Sales Overview Page](./Sales%20Overview.png)

### 4. Customer Analytics Page
Monitors repeat order metrics, customer acquisition channels, and top revenue-generating customers.

![Customer Page](./Customer.png)

### 5. Inventory Management Page
Features stock level heatmaps, turnover ratios, and automated low-stock warnings to avoid dark-store stockouts.

![Inventory Page](./Inventory.png)

### 6. Feedbacks & Sentiment Page
Categorizes qualitative customer feedback (Positive, Neutral, Negative) and highlights common sentiment keywords.

![Feedback Page](./Feedback.png)

### 7. Marketing ROI Page
Evaluates ad spend performance across acquisition channels (Social, Search, Email) and compares campaign ROI.

![Marketing Page](./Marketing.png)

---

## 💡 Business Impact & Recommendations

1. Logistics Optimization: High-volume bottlenecks occur between 7 PM and 10 PM. Reallocating delivery partner shifts during peak evening hours reduces delayed delivery rates.
2. Stockout Prevention: Low-stock alerts flagged fast-moving dairy and snack SKUs early, improving dark-store replenishment efficiency.
3. Marketing Efficiency: Referral and Organic acquisition channels delivered higher ROI compared to paid social ads, pointing to potential ad-budget reallocation opportunities.

---

## 📁 Repository Structure

blinkit-quick-commerce-dashboard/
│
├── Blinkit Dashboard - V1.pbix      # Main Power BI Report File
├── Customer.png                     # Dashboard Screenshot
├── Feedback.png                     # Dashboard Screenshot
├── Home.png                         # Dashboard Screenshot
├── Inventory.png                    # Dashboard Screenshot
├── Marketing.png                    # Dashboard Screenshot
├── Overview.png                     # Dashboard Screenshot
├── Sales Overview.png               # Dashboard Screenshot
└── README.md                        # Project Documentation

---

## ⚙️ Setup & Installation

1. Clone the repository:
   git clone https://github.com/Aditya66050177/blinkit-quick-commerce-dashboard.git

2. Download & View Dashboard:
   - Open Blinkit Dashboard - V1.pbix directly using Power BI Desktop.

---

## 🤝 Author & Contact

Aditya M Patil
* LinkedIn: https://linkedin.com/in/your-profile
* GitHub: https://github.com/Aditya66050177
