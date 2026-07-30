# 📊 Amazon Sales Performance Dashboard | Power BI Project

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-00589C?style=for-the-badge&logo=microsoft&logoColor=white)](https://learn.microsoft.com/en-us/dax/)
[![Data Visualization](https://img.shields.io/badge/Data_Visualization-0275D8?style=for-the-badge)](https://powerbi.microsoft.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## 📌 Executive Summary

The **Amazon Sales Performance Dashboard** is an interactive Power BI analytics solution designed to evaluate e-commerce sales performance, order fulfillment efficiency, product category revenue, and customer purchasing behaviors between **March 2022 and May 2022**.

By leveraging custom **DAX measures**, **Power Query ETL transformations**, and interactive data visualizations, this dashboard provides actionable business insights to optimize inventory management, reduce order cancellations, and improve merchant vs. Amazon fulfillment strategy.

---

## 🖼️ Dashboard Preview

![Amazon Sales Performance Dashboard](assets/dashboard_screenshot.png)

> *Note: Save your dashboard screenshot in the `assets/` folder as `dashboard_screenshot.png` to render it in GitHub.*

---

## 📊 Key Performance Indicators (KPIs)

| Metric | Value | Description |
| :--- | :---: | :--- |
| **Total Revenue** | **₹48.44M** | Total sales generated across all categories & fulfillment channels |
| **Total Orders** | **79,999** | Total volume of customer orders processed during the period |
| **Cancellation Rate** | **14.25%** | Percentage of total orders cancelled (11.4K orders) |
| **Avg Order Value (AOV)** | **₹605.54** | Average revenue earned per order transaction |

---

## 💡 Key Business Insights

1. **Top Revenue Driver Categories**:
   - **T-Shirts** dominate revenue generation with **₹24.6M** (~50.8% of total revenue).
   - **Shirts** follow with **₹12.8M** (~26.4%). Together, apparel accounts for over **77%** of overall revenue.
   - **Blazers (₹6.6M)**, **Trousers (₹3.4M)**, and **Perfume (₹0.5M)** round out the remaining top categories.

2. **Fulfillment Comparison (Amazon vs. Merchant)**:
   - **Amazon Fulfillment** significantly outperforms **Merchant Fulfillment** across all apparel sizes (`M`, `L`, `XL`, `XXL`, `S`, `3XL`, `XS`).
   - Sizes **M (~8.9K Amazon vs 5.0K Merchant)** and **L (~9.0K Amazon vs 4.7K Merchant)** are the highest-demand sizes.

3. **Order Status Distribution**:
   - **Shipped**: **48.18K orders** (~60.2%)
   - **Delivered**: **20.41K orders** (~25.5%)
   - **Cancelled**: **11.40K orders** (~14.25%) ⚠️ *Requires operational review to minimize revenue loss.*
   - **Pending**: **0.01K orders** (~0.01%)

4. **Daily Revenue Trends**:
   - Daily revenue shows periodic demand spikes reaching peaks of **₹1.92M/day** around days 7–8 and 15 of the month.
   - Baseline daily revenue remains stable between **₹1.58M – ₹1.85M**.

---

## 🔍 Interactive Dashboard Features & Filters

- 📅 **Date Range Slicer**: Filter data dynamically between `31-03-2022` and `31-05-2022`.
- 🏷️ **Category Slicer**: Analyze sales performance per individual product line (T-shirt, Shirt, Blazer, Trousers, Perfume).
- 📦 **Order Status Slicer**: Isolate Shipped, Delivered, Cancelled, or Pending orders.
- 👤 **Customer Type Slicer**: Segment analysis by customer profile.
- 🚚 **Fulfilment Slicer**: Compare Amazon (FBA) vs. Merchant (FBM) fulfillment methods.
- 🗺️ **State Slicer**: Regional breakdown of sales and order volume across states.

---

## 🧮 Key DAX Measures Used

```dax
// Total Revenue Calculation
Total Revenue = SUM('Amazon Sales'[Amount])

// Total Orders Count
Total Orders = COUNTROWS('Amazon Sales')

// Total Cancelled Orders
Cancelled Orders = 
CALCULATE(
    COUNTROWS('Amazon Sales'),
    'Amazon Sales'[Order Status] = "Cancelled"
)

// Cancellation Rate Percentage
Cancellation Rate = 
DIVIDE([Cancelled Orders], [Total Orders], 0)

// Average Order Value (AOV)
Average Order Value = 
DIVIDE([Total Revenue], [Total Orders], 0)
```

---

## 🛠️ Tech Stack & Skills Used

- **Business Intelligence Tool**: Power BI Desktop
- **Data Modeling & Calculations**: Data Analysis Expressions (DAX)
- **Data Transformation & Cleaning**: Power Query / M Code
- **Data Source**: Amazon E-Commerce Sales Dataset
- **Design & UX**: Professional KPI card layout, custom color palettes, dynamic tooltips, and interactive filtering

---

## 📁 Repository Structure

```gfm
Amazon-Sales-PowerBI-Dashboard/
│
├── 📂 assets/
│   └── dashboard_screenshot.png    # High-resolution dashboard preview image
│
├── 📂 data/
│   └── Amazon_Sales_Report.csv     # Cleaned raw dataset (or sample data)
│
├── 📜 Amazon_Sales_Dashboard.pbix  # Main Power BI Desktop report file
├── 📜 README.md                    # Project documentation
└── 📜 LICENSE                      # License file
```

---

## 🚀 How to View & Run This Project

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/Amazon-Sales-PowerBI-Dashboard.git
   ```
2. **Install Power BI Desktop**: Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) if not already installed.
3. **Open Project File**: Double-click `Amazon_Sales_Dashboard.pbix` to open the report.
4. **Interact with Visuals**: Use the slicers on the left sidebar to filter data by date, category, status, or fulfillment type.

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for details.
