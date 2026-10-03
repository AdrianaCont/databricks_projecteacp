
# EACP Automotive Data Lakehouse

## Executive Summary

EACP Automotive Data Lakehouse is a Data Engineering project built on Azure and Azure Databricks using the Medallion Architecture (Raw, Bronze, Silver, and Gold layers).

The solution ingests automotive data stored in Azure Data Lake Storage Gen2, processes it with PySpark in Azure Databricks, governs it through Unity Catalog, and exposes curated datasets through a Databricks dashboard.

### Business Objective

The objective of the project is to transform raw automotive data into trusted, governed, and analytics-ready information that can be consumed by business users and reporting tools.

### Solution Overview

The project processes two datasets:

- Automobile_data.csv
- EACP_Automobile_Manufacturers.csv

The architecture follows the Medallion pattern:

### Raw Layer

Stores the original CSV files in Azure Data Lake Storage Gen2.

### Bronze Layer

Performs data ingestion and preserves source traceability.

Generated tables:

- automobile_raw
- automobile_manufacturers_raw

### Silver Layer

Performs:

- Data cleansing
- Data type conversion
- Duplicate removal
- Data quality validation
- Dataset enrichment through joins

Generated table:

- automobile_enriched

### Gold Layer

Creates business-oriented datasets for analytics and reporting.

Generated tables:

- automobile_kpis
- automobile_by_make
- automobile_by_fuel_type
- top_expensive_cars

### Security and Governance

The solution uses:

- Azure Managed Identity
- Access Connector for Azure Databricks
- Unity Catalog
- Role-based access control (RBAC)

This approach eliminates the need to store credentials inside notebooks while providing centralized governance.

### Analytics Outcomes

The solution delivers:

- Executive KPIs
- Average vehicle price analysis
- Manufacturer benchmarking
- Fuel type distribution analysis
- Most expensive vehicles analysis

### Technology Stack

- Azure Data Lake Storage Gen2
- Azure Databricks
- Unity Catalog
- Delta Lake
- PySpark
- Databricks Jobs
- Databricks AI/BI Dashboards
- GitHub

### Project Value

This project demonstrates an end-to-end modern data platform capable of securely ingesting, transforming, governing, and analyzing data while following industry best practices for Lakehouse architectures.

---

## Architecture

Raw Files
↓
Bronze Tables
↓
Silver Enriched Data
↓
Gold Business Data
↓
Databricks Dashboard

---

## Repository Structure

```text
eacp-automotive-lakehouse/
│
├── proceso/
│   ├── 01_eacp_bronze_ingestion.py
│   ├── 02_eacp_silver_transformation.py
│   └── 03_eacp_gold_analytics.py
│
├── datasets/
│   └── EACP_Automobile_Manufacturers.csv
│
├── docs/
├── resources/
├── .github/
└── README.md
```
