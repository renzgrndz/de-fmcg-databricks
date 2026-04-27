# 🏗️ FMCG Data Engineering Project (Lakehouse Architecture with Databricks)

## 📌 Overview
This project is an **end-to-end data engineering pipeline** built using the **Databricks Free Edition**, designed for both beginners and advanced practitioners.

The use case is based on a real-world **FMCG (Fast-Moving Consumer Goods)** scenario where a large retail company acquires a smaller company. The objective is to **consolidate data from both organizations into a unified lakehouse architecture** for analytics and reporting.

---

## 🎯 Business Problem
When companies merge, their data systems are often fragmented. This project solves:

- Data inconsistency across systems  
- Lack of centralized reporting  
- Difficulty in generating business insights  

**Solution:** Build a scalable ETL pipeline that integrates and transforms data into a single source of truth.

---

## 🏗️ Architecture

### 🔷 High-Level Architecture Diagram

```mermaid
flowchart LR
    A[Source Systems<br>Company A & Company B] --> B[Amazon S3 (Raw Data)]
    
    B --> C[Bronze Layer<br>Raw Ingestion]
    C --> D[Silver Layer<br>Cleaned & Transformed]
    D --> E[Gold Layer<br>Business Aggregates]

    E --> F[BI Dashboard]
    E --> G[Genie Query Engine]

    subgraph Databricks Lakehouse
        C
        D
        E
    end
