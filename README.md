# 🚀 PySpark + DBT End-to-End Data Engineering Project

## 📌 Project Overview

This project demonstrates a complete **end-to-end data pipeline** using:

* ⚡ PySpark (Data Processing)
* 🧱 DBT (Data Transformation)
* 🏗️ Medallion Architecture (Bronze → Silver → Gold)
* ☁️ Databricks (Execution Environment)

The pipeline ingests raw CSV data, processes it using PySpark, and applies business transformations using DBT.

---

## 🏗️ Architecture

```
Source Data (CSV)
        ↓
Bronze Layer (Raw Ingestion - PySpark)
        ↓
Silver Layer (Cleaned Data - DBT)
        ↓
Gold Layer (Business KPIs & Snapshots - DBT)
```

---

## 📂 Project Structure

```
PySpark_DBT_Project/
│
├── Notebooks/
│   ├── bronze_ingestion.ipynb
│   ├── silver_transformation.ipynb
│   └── custom_utils.py
│
├── Source data/
│   ├── customers.csv
│   ├── drivers.csv
│   ├── locations.csv
│   ├── payments.csv
│   ├── trips.csv
│   └── vehicles.csv
│
├── PySpark_DBT/
│   ├── models/
│   ├── snapshots/
│   ├── macros/
│   ├── analyses/
│   ├── target/
├── README.md
```

---

## 🔄 Data Pipeline Flow

### 1️⃣ Data Ingestion (Bronze Layer)

* Raw CSV files are loaded using PySpark
* Data stored in Databricks tables

### 2️⃣ Data Transformation (Silver Layer)

* Data cleaned and structured using DBT models
* Removed nulls and standardized formats

### 3️⃣ Business Layer (Gold Layer)

* Created business-ready datasets
* Implemented **incremental models**
* Applied **SCD Type 2 using DBT snapshots**

---

## ⚙️ Key Features

* ✅ End-to-End Data Pipeline
* ✅ Incremental Data Loading
* ✅ SCD Type 2 Implementation
* ✅ Modular DBT Models
* ✅ Scalable Architecture (Medallion)
* ✅ GitHub Version Control

---

## 📊 Sample Use Cases

* Track trip details and status
* Analyze payment methods
* Monitor driver and customer activity
* Historical tracking using snapshots

---

## 🛠️ Tech Stack

| Tool       | Purpose         |
| ---------- | --------------- |
| PySpark    | Data Processing |
| DBT        | Transformation  |
| Databricks | Execution       |
| GitHub     | Version Control |

---

## 🚀 How to Run

### Step 1: Load Data

Run PySpark notebooks:

* `bronze_ingestion.ipynb`
* `silver_transformation.ipynb`

### Step 2: Run DBT Models

```
dbt run
```

### Step 3: Run Snapshots

```
dbt snapshot
```

---

## 📌 Key Learnings

* Building scalable pipelines using Medallion architecture
* Handling incremental loads in DBT
* Implementing SCD Type 2
* Integrating PySpark with DBT
