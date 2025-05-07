# Swiggy End-to-End Data Engineering Project using Snowflake

This project simulates the data ecosystem of Swiggy — a major food aggregator — using a complete ELT data engineering pipeline. It covers everything from data loading and transformation in **Snowflake** to visualization using **Streamlit**.


## Architecture Overview

> End-to-End Flow: Raw CSV ➜ Staging ➜ Cleansing ➜ Consumption Layer ➜ KPIs ➜ Dashboard

---

## ⚙️ Tech Stack

| Tool        | Purpose                             |
|-------------|-------------------------------------|
| Snowflake   | Cloud Data Warehouse                |
| Streamlit   | Interactive KPI Dashboard           |
| Python      | Scripting for automation            |
| CSV         | Simulated data input                |

---

## 🗂️ Folder Structure

```
Swiggy_EndtoEnd_Project_using_Snowflake/
├── SQL_Scripts/                          # SQL DDL/DML scripts for Snowflake
│   ├── 01 Create DW, DB & Schema.sql
│   ├── 02-13 Entity & Fact Table Scripts
│   └── 13 KPI Views.sql
│
├── Streamlit_App_Code_Python/
│   └── Swiggy_Revenue_Dashboard_Streamlit_Code.py  # Final KPI Dashboard
│
└── README.md
```

---

## 🔄 Data Pipeline Steps

### 1️⃣ Load Data into Snowflake
- Use **Snowsight** or SnowSQL `COPY INTO` commands
- Files: `customers.csv`, `orders.csv`, etc.

### 2️⃣ Create and Stage Tables
- Scripts: `01 Create DW, DB & Schema.sql`, staging table DDLs

### 3️⃣ Clean & Transform
- Scripts: `02-10` for all entities
- `11 Date Dim.sql` and `12 Order Fact.sql` handle dimensional modeling

### 4️⃣ KPIs & Views
- Use `13 KPI Views.sql` for insights like revenue, order volume, avg. delivery time

### 5️⃣ Dashboard
- `Swiggy_Revenue_Dashboard_Streamlit_Code.py` builds an interactive Streamlit app

---

## 📈 Sample KPIs

- 🔁 Total Orders by Location
- 🛵 Avg. Delivery Time by City
- 💰 Revenue by Restaurant
- ⭐ Ratings and Customer Retention

---

## 💡 Key Learnings

- Data modeling with Fact/Dim structure
- Snowflake staging using `$` file notation
- Running delta loads using `COPY INTO`
- Designing consumption layers and views
- Dashboarding using Python and Streamlit

---

## 📌 Future Scope

- Add dbt transformation layer
- Integrate Airflow to automate stages
- Push data from APIs (e.g., Swiggy live data)
- Add CI/CD for SQL and dashboard code

