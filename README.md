# 📈 Data Lakehouse Project: End-to-End Medallion Pipeline

This repository contains a professional-grade Data Engineering pipeline following the **Medallion Architecture**. The project demonstrates how to ingest, clean, and analyze data by combining the high-performance compute of **Databricks SQL Warehouse** with the flexible Python environment of **Google Colab**.

---

## 🏗️ The Medallion Architecture & Implementation

### ⚙️ [**0. Infrastructure & SQL Initialization**](Codes_Scripts/Lakehouse_Initiation.ipynb)
The foundation of the project where the environment is prepared:
* **Warehouse Setup**: Configuration of the Databricks SQL Warehouse compute resources.
* **Schema Definition**: SQL scripts to initialize the `sales` catalog and the `bronze`, `silver`, and `gold` schemas.

### 🥉 [**1. Bronze Layer: Raw Ingestion**](Codes_Scripts/Bronz_Layer)
The landing zone for raw data:
* **Volume Storage**: Raw files are staged in **Databricks Volumes**.
* **Delta Conversion**: Data is loaded into managed Delta tables, preserving the original state while adding essential ingestion metadata.

### 🥈 [**2. Silver Layer: Data Refinement & ETL**](Codes_Scripts/Silver_Layer)
The "Source of Truth" where data is transformed into a high-quality format:
* **ETL Pipeline**: Implementation of white-space trimming, column renaming, and duplicate removal.
* **Standardization**: Data types are strictly enforced and text fields are normalized (UPPERCASE) for unified reporting.

### 🥇 [**3. Gold Layer: Business Intelligence & Analysis**](ICodes_Scripts/Gold_Layer)
The presentation layer optimized for business insights:
* **Hybrid Connectivity**: A secure bridge is established between Google Colab and Databricks.
* **Dynamic Python Integration**: Silver tables are dynamically extracted as **Pandas DataFrames** to allow for rapid Python-based analysis and visualization without sacrificing cloud compute power.

---



## 🛠️ Tech Stack
* **Cloud Platform:** Databricks (SQL Warehouse & Unity Catalog)
* **Local IDE:** Google Colab
* **Data Engine:** Spark / Delta Lake
* **Libraries:** `databricks-sql-connector`, `sqlalchemy-databricks`, `pandas`

---

## 🚀 Getting Started

### 1. Databricks Configuration
Ensure your SQL Warehouse is running and you have generated a **Personal Access Token (PAT)** from your Databricks User Settings.

### 2. Google Colab Secrets (🔑)
To run the notebooks, add the following keys to your Colab "Secrets" tab:
* `DB_HOST`: Your Databricks workspace URL (e.g., `adb-xxx.net`).
* `DB_PATH`: The HTTP Path of your SQL Warehouse.
* `DB_TOKEN`: Your Personal Access Token.

### 3. Execution Order
1. Run the **[Initialization Script](Codes_Scripts/Lakehouse_Initiation.ipynb)**.
2. Execute the **Bronze** and **Silver** notebooks in Databricks.
3. Use the **Gold** notebook in Colab to pull final results and generate insights.

---
