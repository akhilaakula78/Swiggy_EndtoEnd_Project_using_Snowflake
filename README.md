
# Swiggy End-to-End Data Engineering Project using Snowflake

This project simulates the data ecosystem of Swiggy — a major food aggregator — using a complete ELT data engineering pipeline. It covers everything from data loading and transformation in **Snowflake** to visualization using **Streamlit**.

## Entities

![Entities](/Entities.png)

🔗 **GitHub Repository:** [Swiggy_EndtoEnd_Project_using_Snowflake](https://github.com/akhilaakula78/Swiggy_EndtoEnd_Project_using_Snowflake)

---

## Architecture Overview

> **End-to-End Flow:** Raw CSV ➜ Staging ➜ Cleansing ➜ Consumption Layer ➜ KPIs ➜ Dashboard

![Architecture Overview](/Data%20Flow%20Architecture.jpg)

---

## Tech Stack

| Tool        | Purpose                             |
|-------------|-------------------------------------|
| Snowflake   | Cloud Data Warehouse                |
| Streamlit   | Interactive KPI Dashboard           |
| Python      | Scripting for automation            |
| CSV         | Simulated data input                |

---

##  Data Pipeline Steps

### Load Data into Snowflake
- Use **Snowsight** UI or SnowSQL with `COPY INTO` commands
- Files include `customers.csv`, `orders.csv`, `restaurants.csv`, etc.

### Create and Stage Tables
- Schema and table creation handled by: `01 Create DW, DB & Schema.sql`
- Initial raw load into staging layer (Bronze)

### Clean & Transform
- Transformations in Clean Layer using `02-10` scripts
- `11 Date Dim.sql` for generating a dynamic date dimension
- `12 Order Fact.sql` to assemble a granular fact table

### KPIs & Views
- `13 KPI Views.sql` builds views for business metrics like:
  - Revenue by restaurant
  - Orders over time
  - Delivery performance

### Dashboard
- Built using `Swiggy_Revenue_Dashboard_Streamlit_Code.py`
- Interactive interface for exploring KPIs across years/months

---

## Sample KPIs Tracked

- Total Orders by Location
- Avg. Delivery Time by City
- Revenue by Restaurant
- Ratings and Customer Retention
- Month-over-Month Growth
- Revenue by Customer Segment

---

## Key Learnings

- Designing data models using Fact and Dimension tables
- Snowflake COPY operations with `$`-notation for internal stages
- Using **Streams and Merge** for delta load automation
- Implementing **Slowly Changing Dimensions (SCD Type 2)**
- Creating self-service BI dashboards in Python using **Streamlit**

---

## Future Scope

- Integrate **dbt** for modular SQL transformations
- Add **Airflow** or Snowflake Tasks to orchestrate the pipeline
- Ingest real-time or API-based feeds (e.g., Swiggy’s live data)
- Add **CI/CD** workflows for SQL and Streamlit deployment

---

## Acknowledgment

This project draws conceptual and structural inspiration from the YouTube channel [Data Engineering Simplified](https://www.youtube.com/@DataEngineeringSimplified). The tutorial videos offered clear guidance for pipeline design and best practices in Snowflake.
