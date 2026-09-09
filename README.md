# 📊 Sales Analytics Dashboard | Power BI

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-00758F?style=for-the-badge&logo=powerbi&logoColor=white)
![Data Analytics](https://img.shields.io/badge/Data_Analytics-000000?style=for-the-badge&logo=github&logoColor=white)

An end-to-end **Business Intelligence & Data Visualization Project** analyzing sales performance, profitability trends, and product category efficiency. This project explores revenue distribution by segment, regional performance, monthly trends, and profit margin breakdowns to answer key business questions.

---

## 📌 Executive Summary

This Power BI report provides a comprehensive executive overview of sales operations. The analysis bridges financial metrics (sales revenue, profit) with operational metrics (category performance, regional distribution, profit margins) to guide strategic decision-making in pricing, inventory, and market expansion.

### 💡 Key Metrics At A Glance
* **Total Sales Revenue:** ~₹2.3M+
* **Top Performing Segment:** Home Office (50.32% of total sales)
* **Highest Margin Category:** Technology (17.22% profit margin)
* **Peak Sales Month:** September (₹309K)

---

## 📊 Dashboard Pages & Business Questions

The report is structured around standard **Business Intelligence Storytelling Principles**, framing every visualization around a specific business question.

---

### Page 1: Sales Performance Overview
> **Objective:** Provide high-level executive KPIs and sales distribution metrics by segment, region, and category.

| Visual Type | Business Question Answered | Key Insight / Finding |
| :--- | :--- | :--- |
| **KPI Cards** | *What is the overall scale of sales performance?* | **₹2.3M+** total sales, with **Home Office** leading all segments[cite: 1]. |
| **Donut Chart** | *Which customer segments drive the most revenue?* | **Home Office** (50.32%) dominates, followed by **Corporate** (30.77%) and **Consumer** (18.92%)[cite: 1]. |
| **Pie Chart** | *How is sales distributed across regions?* | **East** (31.86%) and **Central** (31.80%) lead, with **West** close behind (29.74%)[cite: 1]. |
| **Column Chart** | *Which product categories generate the highest sales?* | **Technology** and **Furniture** are top contributors, with Office Supplies lagging[cite: 1]. |
| **Detail Table** | *Which sub-categories are the top performers?* | Highlights top sub-categories like **Copiers, Phones, and Accessories**[cite: 1]. |

---

### Page 2: Monthly Trends & Profitability Deep Dive
> **Objective:** Identify seasonal patterns in sales and profit, and analyze profit margins by category and sub-category.

| Visual Type | Business Question Answered | Key Insight / Finding |
| :--- | :--- | :--- |
| **Line Chart** | *What are the seasonal trends in sales and profit?* | Sales peak in **March (₹211K)** and **September (₹309K)**, with sharp drops in mid-year (May–August) and year-end (Oct–Dec)[cite: 1]. |
| **Horizontal Bar** | *Which categories have the highest profit margins?* | **Furniture** leads with **17.45%** margin, followed closely by **Technology** (17.22%)[cite: 1]. |
| **Matrix / Table** | *How are profit margins distributed across sub-categories?* | Top sub-categories: **Labels (43.90%)**, **Paper (42.28%)**, **Envelopes (37.21%)**. Deep loss-makers: **Bookcases (-₹44K)**, **Tables (-₹18K)**[cite: 1]. |
| **Clustered Bar** | *Which sub-categories are the most profitable or loss-making?* | Highlights profit margin ranges from **+43.90%** (Labels) to deeply negative figures (-118.71% in some Office Supplies sub-categories)[cite: 1]. |

---

## 🛠️ Data Modeling & DAX Measures

### Key DAX Measures & Calculations

```dax
// Total Sales
Total Sales = SUM(sales[Sales Amount])

// Total Profit
Total Profit = SUM(sales[Profit])

// Profit Margin %
Profit Margin % = 
DIVIDE(
    SUM(sales[Profit]),
    SUM(sales[Sales Amount]),
    0
)

// Sales by Segment
Sales by Segment = 
SUMMARIZE(
    sales,
    sales[Segment],
    "Total Sales", SUM(sales[Sales Amount])
)

// Profit Margin by Category
Profit Margin by Category = 
SUMMARIZE(
    sales,
    sales[Category],
    "Margin %", DIVIDE(SUM(sales[Profit]), SUM(sales[Sales Amount]), 0)
)

// Monthly Sales Trend
Monthly Sales = 
SUMMARIZE(
    sales,
    sales[Month],
    "Total Sales", SUM(sales[Sales Amount]),
    "Total Profit", SUM(sales[Profit])
)

// Profit Margin Range Group (Calculated Column)
Profit Margin Group = 
SWITCH(
    TRUE(),
    [Profit Margin %] <= 0.10, "0-10%",
    [Profit Margin %] <= 0.20, "10.01-20%",
    [Profit Margin %] <= 0.30, "20.01-30%",
    [Profit Margin %] <= 0.50, "30.01-50%",
    [Profit Margin %] <= 1.00, "50.01-100%",
    [Profit Margin %] <= 1.50, "100.01-150%",
    "150.01-200%"
)

### Getting Started
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/your-repository.git](https://github.com/your-username/your-repository.git)


<img width="855" height="498" alt="image" src="https://github.com/user-attachments/assets/b5851c8b-0d93-472b-84a3-eeb8746d1412" />

<img width="855" height="498" alt="image" src="https://github.com/user-attachments/assets/257c1839-cb1a-4e55-a627-7a0077aa1057" />



   
