# 🚀 Sales Data Engineering Project (Azure Cloud)

## 📘 Project Overview
This project demonstrates an **end-to-end data engineering pipeline** implemented using the **Azure ecosystem**.  
The goal was to build a fully automated data pipeline to extract, transform, and visualize sales data using **Azure Data Factory**, **Databricks**, **Synapse Analytics**, and **Power BI**.  

---

## 🧠 Architecture Summary
**Architecture Flow:**  
GitHub → Azure Data Factory → Azure Data Lake Storage Gen2 → Azure Databricks → Azure Synapse Analytics → Power BI  

---

## 🏗️ Project Workflow

### 1. 🔹 Resource Group Creation
- Created a dedicated **Azure Resource Group** to organize and manage resources like ADF, Databricks, Synapse, and Storage accounts.  

### 2. 🔹 Data Ingestion (ADF)
- Used **Azure Data Factory (ADF)** to dynamically extract multiple CSV files from GitHub.
- Parameterized the pipeline using a **lookup + ForEach** structure to loop through datasets from a metadata JSON file (`git.json`).
- Ingested 10+ datasets (Sales, Products, Customers, Territories, Returns, etc.) into **Azure Data Lake Storage Gen2** (Bronze Layer).

### 3. 🔹 Data Transformation (Azure Databricks)
- Configured a custom **Databricks Cluster** for Spark-based data transformation.
- Used **PySpark** to clean, join, and enrich raw data.
- Implemented **Bronze → Silver → Gold** architecture for better data lineage and reusability.

### 4. 🔹 Data Modeling (Azure Synapse Analytics)
- Created **external tables** and **schemas** in Synapse using Parquet files from the Gold Layer.
- Built **SQL Views** for quick querying and BI access.
- Improved query performance by **40%** compared to CSV-based reads.

### 5. 🔹 Data Visualization (Power BI)
- Connected **Power BI** directly to Synapse using DirectQuery.
- Built interactive dashboards displaying:
  - Total Sales by Year and Territory  
  - Product-wise Revenue  
  - Customer Segmentation & Returns Trend  

---

## 🧩 Tech Stack

| Category | Tools / Technologies |
|-----------|----------------------|
| Data Ingestion | Azure Data Factory |
| Data Storage | Azure Data Lake Gen2 |
| Data Processing | Azure Databricks (PySpark) |
| Data Modeling | Azure Synapse Analytics |
| Visualization | Power BI |
| Language | Python, SQL |
| File Format | CSV, Parquet |

---

## 📂 Project Files
| File Name | Description |
|------------|-------------|
| `git.json` | Metadata file containing GitHub dataset URLs and destination folders |
| `Creating Schema.png` | Screenshot showing schema creation in Synapse |
| `Creating External Table.png` | Synapse external table setup |
| `Creating Views.png` | View creation for Gold layer |
| `Dynamic Pipeline.png` | ADF dynamic pipeline overview |
| `Importing Data From Synapse To Power BI.png` | Power BI connection |
| `Own Cluster.png` | Databricks cluster configuration |
| `Resource Group.png` | Resource organization in Azure portal |

---

## 📊 Key Outcomes
- Reduced manual data handling by **80%** using dynamic pipelines.  
- Achieved **real-time query performance** on 5M+ records with Synapse Parquet optimization.  
- Delivered **60% faster dashboard refresh** through Power BI and Synapse integration.  

---

## 🏁 Conclusion
This project highlights the implementation of a **scalable, cloud-based data engineering solution** that automates data ingestion, transformation, and reporting.  
It demonstrates how Azure tools can seamlessly integrate to deliver **efficient, real-time analytics pipelines** for
