# superstore_sales_analysis_sales_profit-loss
# Superstore Sales Performance Analysis & Interactive BI Dashboard

## 📌 Project Overview
This repository contains an end-to-end data analytics and business intelligence project designed to analyze retail operational performance, profitability, and customer behavior. Leveraging a transactional dataset of a multi-regional superstore marketplace, this project implements a two-tiered architecture:
1. **Data Engineering & Exploratory Data Analysis (EDA):** A programmatic pipeline developed in Python (Pandas) to ingest, clean, standardize, and engineer transactional features.
2. **Business Intelligence Visualization:** An interactive executive dashboard engineered inside Microsoft Power BI to deliver deep visual diagnostics into sales trajectories, regional distributions, and product line profit margins.

---

## 📁 Repository Structure

The project environment is composed of the following core deliverables:
* **`Sample - Superstore.csv`**: The raw transactional ledger containing retail commerce records spanning customer profiles, spatial attributes, and product sales statistics.
* **`amazonsales.ipynb`**: A comprehensive Jupyter Notebook detailing the data preprocessing, format casting, structural sanitation, and descriptive statistical verification performed in Python.
* **`PRIME_SYSTEM_PROJECT1.pbix`**: The fully deployed Power BI Desktop application containing interactive canvas layers, relational data views, and multi-dimensional business slicers.

---

## 📊 Dataset Schema & Dimensions

The primary dataset (`Sample - Superstore.csv`) tracks purchase orders across 21 columns capturing discrete business segments:
* **Temporal Identifiers:** `Order Date`, `Ship Date`
* **Operational Logs:** `Row ID`, `Order ID`, `Ship Mode`
* **Customer Profiles:** `Customer ID`, `Customer Name`, `Segment` (Consumer, Corporate, Home Office)
* **Geographic Attributes:** `Country`, `City`, `State`, `Postal Code`, `Region`
* **Inventory Taxonomy:** `Product ID`, `Category`, `Sub-Category`, `Product Name`
* **Financial Performance Indicators:** `Sales`, `Quantity`, `Discount`, `Profit`

---

## ⚙️ Data Preprocessing & Analytics Pipeline (`amazonsales.ipynb`)

The data preparation engine programmatically enforces data integrity and prepares clean tables for downstream ingestion. The execution logic inside the notebook includes:

* **Robust Data Ingestion:** Loads the comma-separated data tables utilizing `latin1` encoding strings to avoid byte-sequence translation faults during ingestion.
* **Null-Value Audit:** Runs a full column-wise missing values query (`df.isna().sum()`), confirming a 100% complete dataset with zero missing values across all dimensional features.
* **Integrity Verification:** Inspects rows via a programmatic boolean filter (`df.duplicated().any()`) to verify that no exact duplicate rows taint the ledger.
* **Schema Standardization:** Converts all text headers into strict lowercase and replaces space gaps with clean underscores (e.g., `Order ID` $\rightarrow$ `order_id`, `Ship Date` $\rightarrow$ `ship_date`) for standardized backend column querying.
* **Type Casting:** Casts data types from simple objects/strings into structured `datetime64` representations for both `order_date` and `ship_date` attributes.
* **Feature Engineering:** Extracts granular year and month fields (`df['year']`, `df['month']`) from parsed order timestamp objects to facilitate advanced seasonality and year-over-year reporting.
* **Descriptive Statistical Profiling:** Generates metrics snapshots across numerical categories—such as analyzing the distribution profile of the `discount` field (revealing a mean discount rate of ~15.62% and a maximum promotional discount threshold of 80%).

---

## 📈 Power BI Interactive Dashboard Layout (`PRIME_SYSTEM_PROJECT1.pbix`)

The processed data feeds into a dynamic Power BI workspace, building out interactive report view levels configured for business managers:
* **Executive Scorecards:** Highlights key performance parameters including Total Consolidated Sales, Net Gross Profit, Total Units Transacted, and Cumulative Margins.
* **Spatiotemporal Map Panels:** Uses geospatial variables (`state`, `region`) mapped against performance indicators to pinpoint underperforming areas versus major profit hubs.
* **Category Cross-Filtering Matrices:** Pairs product classifications (*Furniture*, *Office Supplies*, and *Technology*) alongside their underlying nested sub-categories to isolate high-volume revenue generators from margin-draining inventory lines.
* **Time-Series Slicers:** Powered by the engineered `year` and `month` fields, this component allows users to seamlessly slice timelines to evaluate holiday seasonal peaks, monthly growth metrics, and delivery speed lags.

<img width="467" height="332" alt="image" src="https://github.com/user-attachments/assets/da83c9d8-0601-4f16-bbf2-900b2e476781" />
<img width="629" height="305" alt="image" src="https://github.com/user-attachments/assets/3cfc9168-3511-438c-a8d8-dbeb8822795c" />
<img width="587" height="329" alt="image" src="https://github.com/user-attachments/assets/5cec407e-f378-460d-b95c-45ec6400554f" />

