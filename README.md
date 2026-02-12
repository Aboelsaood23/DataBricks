# 📈 Data Lakehouse Project: End-to-End Medallion Pipeline

This project demonstrates a complete Data Engineering pipeline using the **Medallion Architecture**. We transition raw data through three distinct stages—Bronze, Silver, and Gold—integrating **Databricks** for heavy lifting and **Google Colab** for analytical agility.

---

## 🏗️ The Medallion Architecture

### 🥉 [**Bronze Layer: Raw Ingestion**](Codes_Scripts/Bronz_Layer)
The entry point for our data.
* **Volume Storage**: Raw files were initially staged in **Databricks Volumes**.
* **Initial Loading**: We performed the primary ingestion, converting raw files into managed Delta tables to ensure data persistence and schema enforcement.

### 🥈 [**Silver Layer: Data Refinement & ETL**](Codes_Scripts/Silver_Layer)
The "Source of Truth" where data is cleaned and standardized.
* **ETL Operations**: Applied rigorous cleaning including white-space trimming, column renaming, and duplicate removal.
* **Data Integrity**: Enforced strict data types and converted text to uniform casing (uppercase) to ensure consistency across all records.
* **Optimization**: Prepared the data for high-performance querying.

### 🥇 [**Gold Layer: Business Intelligence & Analysis**](Codes_Scripts/Gold_Layer)
The final curated layer designed for stakeholders and decision-makers.
* **Hybrid Integration**: Connected **Google Colab** to the **Databricks SQL Warehouse** to leverage the strengths of both platforms.
* **Dynamic Extraction**: Instead of standard SQL views, we utilized Python to dynamically download Silver tables as **Pandas DataFrames**.
* **Business Readiness**: Aggregated data into final business entities, providing "ready-to-use" results for dashboards and executive reporting.

---

## 🛠️ Tech Stack
* **Storage & Compute:** Databricks (SQL Warehouse & Volumes)
* **IDE & Analysis:** Google Colab
* **Languages:** Python (Pandas, SQLAlchemy, Databricks-SQL)
* **Data Format:** Delta Lake

---

## 🚀 How to Run
1. **Secrets**: Ensure your `DB_HOST`, `DB_PATH`, and `DB_TOKEN` are added to your environment secrets.
2. **Connection**: The notebooks use the `databricks-sql-connector` to bridge the environment.
3. **Execution**: Run the layers in order: Bronze ➡️ Silver ➡️ Gold.
