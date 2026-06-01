# Retail Sales Data Processing and Business Insights Generation

## Overview

This project implements an end-to-end retail data engineering pipeline for ABC Retail Solutions using Python, Pandas, and Power BI. The pipeline ingests raw retail transaction datasets from multiple source systems, performs data cleaning, transformation, validation, PII masking, feature engineering, and generates an analytics-ready dataset for business intelligence reporting.

The final Power BI dashboard provides interactive insights into:

* Revenue trends
* Product performance
* Category analysis
* Regional sales insights
* Payment behavior
* Online vs Offline sales performance

---

# Project Architecture

Excel/CSV Source Files → Python Notebook → Cleaned Retail Dataset → Power BI Dashboard

---

# Tech Stack

* Python
* Pandas
* NumPy
* Jupyter Notebook
* Power BI
* SHA-256 Hashing
* CSV / Excel

---

# Dataset Information

The project uses three datasets:

| Dataset         | Description                              |
| --------------- | ---------------------------------------- |
| Product_Details | Product reference metadata               |
| Retail_Data1    | Retail transactions from source system 1 |
| Retail_Data2    | Retail transactions from source system 2 |

---

# Pipeline Stages

## 1. Data Ingestion

* Loaded multiple retail datasets using Pandas
* Validated schema consistency
* Created separate DataFrames for preprocessing

## 2. Data Cleaning

* Removed duplicate transactions
* Handled missing values
* Filtered invalid quantity records
* Standardized product names and categories
* Parsed date columns into datetime format

## 3. Data Consolidation

* Combined Retail_Data1 and Retail_Data2 using pd.concat()
* Added Source_System tracking column

## 4. Data Enrichment

* Merged retail transactions with Product_Details using Product_ID
* Added standardized product metadata

## 5. Feature Engineering

Created analytical columns including:

* Revenue
* Year
* Month
* Quarter
* Purchase Channel

Revenue Formula:

Revenue = (Quantity × Unit_Price) − Discount

## 6. PII Masking

* Customer emails hashed using SHA-256
* Phone numbers partially masked

## 7. Export

* Exported cleaned dataset to retailfinal.csv
* Loaded final dataset into Power BI

---

# Power BI Dashboard

The Power BI dashboard contains four report pages:

## Revenue Analysis

* Total Revenue KPI
* Avg Order Value
* Revenue Trend by Year
* Revenue by Payment Method
* Online vs Offline Revenue

## Product Performance

* Units Sold by Product
* Revenue by Product
* Revenue Share by Category
* Revenue vs Units Sold Analysis

## Category Trends

* Monthly Revenue by Category
* Revenue by Category per City
* Avg Discount % by Category

## Regional Insights

* Revenue by City
* Revenue Share by City
* Online vs Offline Revenue by City

---

# Key Business Insights

* Total revenue exceeded 1.16 billion
* Electronics emerged as the top-performing category
* Chennai generated the highest city-level revenue
* Online and offline channels contributed almost equally
* High-ticket products generated strong revenue contribution
* Revenue declined from 2025 to 2026 across most categories

---

# Folder Structure

```bash
Project Root/
│
├── Code/
│   ├── ABC_Retail_NeoStats_Pipeline.ipynb
│   ├── ABC_Retail_NeoStats_Pipeline.py
│
├── Documentation/
│   ├── NeoStat_Retail_Documentation.docx
│
├── Power BI/
│   ├── NeoStat retail.pbix
│
├── Dataset/
│   ├── retail_data1.csv
│   ├── retail_data2.csv
│   ├── product_details.csv
│
└── README.md
```

---

# Features

* End-to-end ETL pipeline
* Data cleaning and validation
* PII masking implementation
* Feature engineering
* KPI generation
* Interactive Power BI dashboard
* Category and regional analysis
* Time-series revenue trends

---

# Future Improvements

* Azure Data Factory integration
* PySpark implementation for scalability
* Real-time streaming pipeline
* Automated orchestration
* Cloud deployment

---

# Author

Naman Mishra

Integrated M.Tech – Computation and Data Science
VIT Bhopal University

---

# License

This project is created for educational and assessment purposes as part of the NeoStats Data Engineering assignment.
