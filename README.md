# 📊 Olist E-Commerce Analytics & Business Intelligence Dashboard

An end-to-end Power BI data analytics solution created for the **Olist Brazilian E-Commerce Dataset**. This interactive dashboard turns raw operational and transactional data into actionable commercial insights, logistics analysis, and customer feedback tracking.

---

## 📸 Dashboard Preview

### 1️⃣ Page 1: Sales & Revenue Analytics
![Sales & Revenue Dashboard](./docs/sales_revenue_dashboard.png)

### 2️⃣ Page 2: Operations & Logistics Performance
![Operations & Logistics Dashboard](./docs/operations_logistics_dashboard.png)

### 3️⃣ Data Model Schema (Star Schema)
![Data Model](./docs/data_model.png)

---

## 🎯 Executive Summary & Objectives

- **Sales Growth & Performance:** Evaluate sales trends over time, geographical revenue distribution, payment methods, and product categories.
- **Logistics & Supply Chain Efficiency:** Track fulfillment performance, average delivery duration, late shipment rates, and freight expense impacts.
- **Customer Satisfaction Tracking:** Identify correlations between delivery delays and customer review scores.

---

## 📐 Data Architecture & Modeling (Star Schema)

The project leverages a robust **Star Schema** architecture linking fact tables containing order events with dimensional entities:

### Fact Tables
* **`Fact_Order_Items`**: Contains transactional details including order pricing and individual shipping freight costs.
* **`Fact_Payments`**: Tracks transaction values, installment counts, and payment methods (`Credit Card`, `Boleto`, `Voucher`, etc.).
* **`Fact_Reviews`**: Records customer review scores and qualitative feedback timestamp entries.

### Dimension Tables
* **`Dim_Orders`**: Core master orders table recording lifecycle timestamps (`purchase`, `approved`, `carrier delivery`, `customer delivery`, `estimated delivery`) and status (`delivered`, `shipped`, `canceled`).
* **`Dim_Customers`**: Unique customer identification linked with geographical location state codes.
* **`Dim_Products`**: Item details including category translations (`product_category_name_english`) and dimensional specifications.
* **`Dim_Sellers`**: Information on merchant partners and location origins.
* **`Dim_Geolocation`**: Zip code level spatial geolocation mapping.

---

## 🧮 Key Business Metrics & Analytics Focus

Below is the structured breakdown of the business logic and key analytical indicators calculated across the dashboard:

### 💰 1. Sales & Revenue Analytics Focus
* **Total Revenue:** Measures the gross monetary volume generated from sold products across all regions and categories.
* **Total Orders:** Tracks the unique volume of processed customer purchase transactions.
* **Total Freight:** Aggregates shipping charges across all fulfillment journeys to analyze buyer delivery expenditure.
* **Average Review Score:** Evaluates overall customer feedback and satisfaction ratings on a 1-to-5 scale.

---

### 🚚 2. Operations & Logistics Analytics Focus
* **Average Delivery Days:** Measures the average fulfillment duration (lead time in days) from the initial customer order timestamp to final delivery.
* **On-Time Delivery Rate (%):** Measures logistics reliability by calculating the percentage of orders delivered on or before the promised estimated date.
* **Late Orders Count:** Tracks supply chain bottlenecks by highlighting the volume of shipments that missed their estimated delivery target.

---

## 📊 Dashboard Visuals Breakdown

### Page 1: Sales & Revenue Analytics
* **Header KPIs:** High-level executive cards displaying `Total Revenue`, `Total Orders`, `Total Freight`, and `Avg Review Score`.
* **Revenue by State (Clustered Bar Chart):** Identifies top revenue-generating Brazilian states led by **SP (São Paulo)** ($5.2M), **RJ**, and **MG**.
* **Revenue Trend by Year (Waterfall / Column Chart):** Displays year-over-year commercial growth trajectories across 2016, 2017, and 2018.
* **Quarterly Category Performance (Sankey Flow / Ribbon):** Analyzes seasonal category movements across calendar quarters.
* **Payment Methods Breakdown (Donut Chart):** Highlights transaction volume distribution across payment channels.

### Page 2: Operations & Logistics Performance
* **Logistics KPIs:** Key operational trackers showing `Total Freight Cost` ($2.25M), `Avg Delivery Days` (12.50 Days), `On-Time Rate %` (89.15%), and `Late Orders Count` (7,827 Orders).
* **Orders by Delivery Status (Donut Chart):** Visualizes order distribution categorizing fulfillment status into `On Time`, `Late`, and `Not Delivered Yet`.
* **Avg Delivery Days by State (Bar Chart):** Ranks regional logistics bottlenecks, highlighting states with higher delivery lead times (e.g., **RR**, **AP**, **AM**).
* **Delivery Delays vs. Review Score (Line Chart):** Dual-axis tracking showing how fluctuation in delivery duration directly impacts monthly customer satisfaction ratings.
* **Category Order Density (Treemap):** Interactive volume breakdown across English product categories.

---

## 🎨 UI/UX Design System Specification

* **Canvas Theme:** Monolithic Dark Mode (`#03142A`)
* **Card Containers:** Deep Navy (`#0B192C`)
* **KPI Accent Highlight:** Bright Cyan (`#00FFC2` / `#38BDF8`)
* **Interactive Slicers:** Tile-style page navigators and single/multi-select state and temporal filters.

---

## 🛠️ Tools & Technologies Used
* **Business Intelligence Engine:** Microsoft Power BI Desktop
* **Data Transformation:** Power Query (ETL pipeline & Null value cleanups)
* **Modeling:** Data Analysis Expressions (DAX), Relational Star Schema
* **Source Data:** Olist Brazilian E-Commerce Public Dataset
