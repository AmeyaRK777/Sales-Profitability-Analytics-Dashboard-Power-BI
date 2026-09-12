# 📊 Sales & Profitability Analytics | Power BI Dashboard

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-00758F?style=for-the-badge&logo=powerbi&logoColor=white)
![Data Analytics](https://img.shields.io/badge/Data_Analytics-000000?style=for-the-badge&logo=github&logoColor=white)

An end-to-end **Business Intelligence & Data Analytics Project** examining sales performance and profitability leakage across customer segments, geographic regions, sub-categories, and discounting tiers.

---

## 📌 Executive Summary

Analyzing **10,000 completed orders**, this Power BI dashboard balances high-level revenue metrics with granular profitability diagnostics. The analysis bridges top-line sales tracking with loss-margin investigation to expose severe profit erosion driven by uncontrolled discounting strategies.

### 💡 Key Metrics At A Glance
* **Total Sales Volume:** $2.33M
* **Total Profit:** $292.30K
* **Profit Margin:** 12.56%
* **Total Orders Processed:** 10,000

---

## 📊 Dashboard Pages & Business Questions

The report is structured around **Business Intelligence Storytelling Principles**, addressing top-line execution first before performing root-cause profitability breakdowns.

---

### Page 1: Executive Summary (Sales Analytics Dashboard)
> **Objective:** Answer "What happened?" by establishing high-level business volume, top growth drivers, baseline KPIs, and temporal sales trends.

| Visual Type | Business Question Answered | Key Insight / Finding |
| :--- | :--- | :--- |
| **KPI Cards** | *What is the overall baseline scale and profitability of the business?* | **$2.33M** total sales, **$292.30K** total profit, **12.56%** margin, and **10K** total orders. |
| **Donut Chart** | *Which customer segment drives the majority of revenue?* | **Consumer** leads volume (50.32% / $1.17M), followed by **Corporate** (30.77%) and **Home Office** (18.92%). |
| **Bar Chart** | *Which geographic regions yield top sales performance?* | **West** region dominates ($739.81K / 31.8%), closely followed by **East** ($691.83K / 29.74%). **South** lags at 16.84%. |
| **Line Chart** | *How do revenue and profits trend over the calendar year?* | Performance is steady from Jan to Aug, followed by a massive seasonal surge starting in **September** and peaking in **Nov/Dec**. |
| **Horizontal Bar** | *Which product sub-categories drive the highest net profit?* | **Copiers** yield highest profits ($56K), followed by **Phones** ($45K) and **Accessories** ($42K). |

---

### Page 2: Profitability Deep Dive
> **Objective:** Answer "Why did it happen?" by identifying margin bottlenecks, high-risk discount thresholds, and underperforming product lines.

| Visual Type | Business Question Answered | Key Insight / Finding |
| :--- | :--- | :--- |
| **Category Cards** | *Which overall product categories yield the strongest and weakest margins?* | **Technology** (17.45%) & **Office Supplies** (17.22%) lead; **Furniture** severely underperforms at just **2.61%** margin. |
| **Sub-Category Breakdown** | *What specific item is causing the margin drop in Furniture?* | **Tables** represent the primary loss driver, operating at a net loss of **-$18K (-8.55% margin)**, while Chairs & Furnishings remain profitable. |
| **Matrix Heatmap** | *How do promotional discounts impact profit margins by category?* | High discounts erode profitability. Furniture discounts of **30–40%** result in **-39.21%** margins; **50%+** discounts plummet margins to **-105.91%**. |
| **Clustered Bar** | *Which category displays the highest vulnerability to aggressive discounts?* | **Furniture** flips negative (-10.77%) at modest **20–30%** discounts, whereas **Technology** maintains positive margins (**8.68%**) in the same tier. |

---

## 🛠️ Data Modeling & DAX Measures

### Key DAX Measures & Calculations

```dax
// Average Discount Percentage
Avg_Discount = AVERAGE(Orders[Discount])

// Discount Bucket Grouping (Calculated Column)
Discount Bucket = 
SWITCH(
    TRUE(),
    'Orders'[Discount] <= 0.10, "1. 0-10%",
    'Orders'[Discount] <= 0.20, "2. 10-20%",
    'Orders'[Discount] <= 0.30, "3. 20-30%",
    'Orders'[Discount] <= 0.50, "4. 30-50%",
    "5. 50%+"
)

// Total Order Volume
Order Count = COUNT(Orders[Order ID])

// Global Profit Margin Ratio
Profit Margin = CALCULATE(DIVIDE([Total Profit],[Total Sales],0))

// Total Net Profit
Total Profit = SUM(Orders[Profit])

// Total Sales Revenue
Total Sales = SUM(Orders[Sales])
```

---

## 🎯 Strategic Action Plan & Recommendations

1. **Cap Discount Limits:** Immediately implement systemic discount guards on the sales portal, capping max allowed discounts for Furniture items at 20%.
2. **Restructure Table Strategy:** Audit supply chain costs, pricing tiers, and vendor contracts for Tables to address the -$18K loss margin.
3. **Double-Down on High Performers:** Allocate marketing spend toward high-margin growth drivers in the Consumer segment, prioritizing Copiers, Phones, and Technology categories.


### Getting Started
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/your-repository.git](https://github.com/your-username/your-repository.git)


<img width="855" height="498" alt="image" src="https://github.com/user-attachments/assets/b5851c8b-0d93-472b-84a3-eeb8746d1412" />

<img width="855" height="498" alt="image" src="https://github.com/user-attachments/assets/257c1839-cb1a-4e55-a627-7a0077aa1057" />



   
