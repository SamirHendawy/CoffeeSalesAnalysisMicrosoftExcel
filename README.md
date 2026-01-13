# ☕ Coffee Bean Sales Analysis Dashboard

## 📊 Project Overview
This project is a comprehensive sales performance analysis for a coffee retailer. It transforms raw, fragmented data into an interactive and visually appealing dashboard to drive data-informed business decisions.

---

## 🖥️ Interactive Dashboard Preview
The dashboard provides a high-level overview of sales trends, geographical performance, and customer behavior.

![Coffee Sales Dashboard](Screenshot%202026-01-13%20000820.png)
*Figure 1: Full Interactive Coffee Sales Dashboard*

### Key Dashboard Features:
- **Geographical Analysis:** Visualizing revenue across the US, Ireland, and the UK.
- **Customer Insights:** Identifying the top 5 most valuable customers.
- **Dynamic Filtering:** Slicers for **Roast Type**, **Package Size**, and **Loyalty Card** status.
- **Timeline Slicer:** Filtering sales data across years (2019-2022) and months.

---

## 🛠️ Technical Implementation & Formulas
To build this robust data model, I utilized advanced Excel functions to clean, map, and categorize data.

### 1. Two-Dimensional Lookup (INDEX & MATCH)
I used a manual **INDEX & MATCH** combination to perform a 2D lookup. This dynamically fetches product details by matching both the Product ID (rows) and the specific attribute header (columns).

![INDEX MATCH Formula](ggggggggggggggg.png)
*Formula: `=INDEX(products!$A:$G, MATCH(orders!$D2, products!$A:$A, 0), MATCH(orders!$I$1, products!$A$1:$E$1, 0))`*

### 2. Efficient Data Mapping (XLOOKUP)
To retrieve customer-specific information (like loyalty status or email) based on their unique ID, I implemented the **XLOOKUP** function for better performance and error handling.

![XLOOKUP Formula](Screenshot%202026-01-13%20174513.png)
*Formula: `=XLOOKUP($C2, customers!$A:$A, customers!$G:$G, "", 0, 1)`*

### 3. Data Standardization (Nested IFs)
To ensure the dashboard displays user-friendly product names instead of raw abbreviations, I used **Nested IF statements** to categorize coffee types.

![Nested IF Formula](ifs.png)
*Formula: `=IF($I2="Rob","Robusta",IF($I2="Exc","Excelsa",IF($I2="Ara","Arabica",IF($I2="Lib","Liberica",""))))`*

---

## 📈 Key Insights & Business Analysis
Based on the dashboard results:

* **Market Share:** The **United States** is the dominant market, contributing **$35,639** in total sales.
* **Top Customer:** **Alis Wilmore** is the highest-spending customer with a total of **$317**.
* **Sales Trends:** The line chart shows significant volatility in sales over time, with notable peaks in late 2021 and early 2022 for types like **Arabica** and **Liberica**.

---

## 🚀 Skills Demonstrated
- **Advanced Excel Formulas:** INDEX/MATCH, XLOOKUP, Nested IFs.
- **Data Visualization:** Creating professional charts, slicers, and timelines.
- **ETL Process:** Cleaning and organizing raw data into a structured format for analysis.

## 📂 Files in this Repository
- `coffeeOrdersDataProject.xlsx`: The final workbook containing the data model and dashboard.
- `Raw Data.xlsx`: The original datasets used for the project.