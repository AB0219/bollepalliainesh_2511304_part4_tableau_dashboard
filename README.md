# # Tableau Executive Dashboard - Retail Sales Analysis

## Project Overview

This project presents an interactive Tableau Executive Dashboard developed for a retail leadership team. The dashboard enables executives to monitor sales performance, profitability, customer behavior, regional performance, shipping efficiency, discount impact, and product return patterns. The objective is to support data-driven decision-making through interactive visualizations and business insights.

---

# Business Problem

Retail executives require a centralized dashboard to monitor key business metrics and identify opportunities and risks across different business areas. This project addresses that need by providing an executive dashboard that combines sales trends, profitability analysis, customer segmentation, shipping performance, discount analysis, and return analysis into a single interactive reporting solution.

---

# Dataset Description

The project uses the provided retail sales dataset:

`data/dashboard_sales_data.xlsx`

The dataset includes information such as:

* Order ID
* Order Date
* Ship Date
* Customer Segment
* Region
* State
* City
* Category
* Sub-Category
* Product Name
* Sales
* Profit
* Quantity
* Discount
* Ship Mode
* Return Flag
* Delivery Days
* Customer Rating
* Campaign Channel

---

# Tableau Workbook

The Tableau packaged workbook is stored as:

```text
tableau/executive_dashboard.twbx
```

The workbook contains multiple worksheets and one executive dashboard designed for business leadership.

---

# Calculated Fields Created

The following calculated fields were created in Tableau:

### 1. Profit Margin

```tableau
SUM([profit]) / SUM([sales])
```

Calculates profit as a percentage of total sales.

---

### 2. Cost

```tableau
SUM([sales]) - SUM([profit])
```

Estimates product cost from sales and profit.

---

### 3. Average Order Value

```tableau
SUM([sales]) / COUNTD([order_id])
```

Measures the average revenue generated per order.

---

### 4. Shipping Days

```tableau
DATEDIFF('day',[order_date],[ship_date])
```

Calculates the number of days required to deliver an order.

---

### 5. Shipping Delay Bucket

```tableau
IF [Shipping Days] <= 2 THEN "Fast"
ELSEIF [Shipping Days] <= 5 THEN "Standard"
ELSE "Delayed"
END
```

Categorizes deliveries into shipping performance groups.

---

### 6. Return Rate

```tableau
AVG([return_flag])
```

Calculates the percentage of returned orders.

---

# Dashboard Components

The executive dashboard includes the following visualizations:

* Sales Trend
* Regional Performance
* Category Profitability
* Customer Segment Analysis
* Shipping Performance
* Discount vs Profit Analysis
* Return Analysis

---

# KPI Cards

The dashboard displays the following executive KPIs:

* Total Sales
* Total Profit
* Profit Margin
* Total Orders

---

# Filters Used

Interactive filters available on the dashboard include:

* Region
* Category
* Customer Segment
* Ship Mode
* Order Date

All filters are applied across the dashboard for interactive exploration.

---

# Dashboard Interactions

Dashboard actions were implemented to improve user experience.

Users can:

* Filter charts by selecting regions.
* Interactively explore category performance.
* Analyze customer segments.
* View detailed information using tooltips.
* Apply dashboard-wide filters.

---

# Key Business Insights

The dashboard provides insights including:

* Sales trends over time.
* Regional sales and profitability comparison.
* Category and sub-category profitability.
* Customer segment contribution.
* Impact of discounts on profit.
* Shipping performance by ship mode.
* Product return analysis.
* Business opportunities and operational risks.

Detailed insights are documented in:

```text
outputs/business_insights.md
```

---

# Dashboard Story

The dashboard tells a complete business story by connecting sales performance, profitability, customer behavior, logistics performance, and return analysis into a single executive reporting solution.

The complete business narrative is available in:

```text
outputs/dashboard_story.md
```

---

# Chart Selection Justification

Each visualization was selected based on the business question it answers.

Examples include:

* Line Chart for sales trends.
* Bar Charts for category and regional comparison.
* Scatter Plot for discount versus profit analysis.
* Bar Chart for return analysis.

Detailed explanations are available in:

```text
outputs/chart_selection_justification.md
```

---

# Assumptions

* Missing values were assumed to have minimal impact on overall analysis.
* The `return_flag` field uses binary values (0 = Not Returned, 1 = Returned).
* Delivery days were calculated using Order Date and Ship Date where required.
* Historical data accurately represents business performance during the reporting period.

---

# Limitations

* The dashboard uses historical transactional data only.
* External market conditions are not included.
* Inventory availability is outside the scope of this project.
* Customer feedback and satisfaction metrics are not included.

---

# Repository Structure

```text
part4_tableau_dashboard/
├── data/
│   └── dashboard_sales_data.xlsx
├── tableau/
│   └── executive_dashboard.twbx
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
└── README.md
```

---

# Screenshots Included

The repository contains the following dashboard screenshots:

* `full_dashboard.png`
* `sales_trend_view.png`
* `regional_performance_view.png`
* `category_profitability_view.png`
* `filter_interaction_view.png`

---

# Tools Used

* Tableau Public
* Microsoft Excel
* GitHub
* Markdown

---

# Conclusion

This project demonstrates the design and implementation of an executive-level Tableau dashboard for retail sales analysis. By integrating interactive visualizations, calculated metrics, business insights, and storytelling, the dashboard supports leadership in identifying performance trends, operational risks, and strategic opportunities through data-driven decision-making.
