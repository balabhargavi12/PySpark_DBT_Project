# 🔄 PySpark + DBT Transformation Layer

## 📌 Overview

This module represents the **core transformation layer** of the project, where raw data from the Bronze layer is transformed into clean, structured, and business-ready datasets using **DBT**.

It works on top of data ingested via **PySpark** and stored in Databricks.

---

## 🏗️ Architecture Role

```
Bronze (Raw Data - PySpark)
        ↓
Silver (Cleaned Data - DBT Models)
        ↓
Gold (Business Layer + Snapshots)
```

---

## 📂 Folder Structure

```
PySpark_DBT/
│
├── analyses/        → Ad-hoc SQL analysis
├── macros/          → Reusable DBT logic
├── models/          → Transformation models (Silver/Gold)
├── snapshots/       → SCD Type 2 implementation
├── target/compiled/ → Auto-generated files (ignore)
│
└── README.md
```

---

## 🔄 Transformation Logic

### ✅ Silver Layer

* Data cleaning
* Column standardization
* Null handling
* Data type corrections

### ✅ Gold Layer

* Business-ready datasets
* KPI calculations
* Aggregations

### ✅ Snapshots (SCD Type 2)

* Track historical changes
* Maintain slowly changing dimensions
* Example:

  * Customer updates
  * Trip status history

---

## ⚙️ Key DBT Concepts Used

* 🔹 `ref()` → Model dependency management
* 🔹 `source()` → Read from Bronze tables
* 🔹 Incremental Models → Efficient data loading
* 🔹 Snapshots → SCD Type 2 tracking
* 🔹 Jinja Templating → Dynamic SQL generation

---

## 🚀 How to Run

### Run Models

```id="run1"
dbt run
```

### Run Snapshots

```id="run2"
dbt snapshot
```

### Test Models

```id="run3"
dbt test
```

---

## ⚠️ Important Notes

* Do NOT commit `target/compiled/` (auto-generated files)
* Always define `unique_key` for incremental models
* Ensure `updated_at` column exists for snapshots

---

## 📊 Example Model

```sql id="sql1"
SELECT
    trip_id,
    customer_id,
    driver_id,
    fare_amount,
    trip_status
FROM {{ source('source_bronze', 'trips') }}
```

---

## 🎯 Purpose

This layer ensures:

* Clean and reliable data
* Reusable transformation logic
* Scalable data pipeline design

---

## 👩‍💻 Author

**Golli Bala Bhargavi**

