# 🏠 Home Sales Analysis with PySpark

This project analyzes a dataset of home sales using PySpark's SQL and DataFrame APIs to uncover trends in home prices across time, features, and views. It demonstrates the power of distributed computing for large-scale data processing and performance optimization.

---

## 📑 Table of Contents

1. [Project Overview](#project-overview)
2. [Technologies Used](#technologies-used)
3. [Key SQL Queries & Analysis](#key-sql-queries--analysis)
4. [Performance Optimization](#performance-optimization)
5. [Repository Structure](#repository-structure)
6. [Conclusion](#conclusion)

---

## 📈 Project Overview

The purpose of this project is to:
- Load and explore home sales data using PySpark
- Write SQL queries to analyze price trends by features such as year, number of bedrooms, bathrooms, and views
- Use caching and Parquet partitioning to improve performance
- Compare execution time across uncached, cached, and Parquet-optimized queries

---

## 🛠 Technologies Used

- Python 3.10+
- PySpark
- AWS S3 (for source CSV)
- Apache Parquet (for optimized data storage)
- Jupyter Notebook

---

## 🔍 Key SQL Queries & Analysis

The notebook answers the following questions:

1. **Average price for 4-bedroom homes per year**
2. **Average price of 3 bed / 3 bath homes per build year**
3. **Average price of 3 bed / 3 bath / 2-floor homes ≥2000 sqft per build year**
4. **Average price by view rating (only if average ≥ $350,000)**

---

## ⚡️ Performance Optimization

To compare performance, the following were implemented:
- **Caching** of the Spark SQL temp table (`home_sales`)
- **Partitioning** of data using the `date_built` field and writing to Parquet format
- **Execution time** measured for:
  - Raw SQL query
  - Cached table
  - Parquet-optimized query

---

## 📂 Repository Structure

```
Home_Sales/
├── home_sales_partitioned/       # Parquet output partitioned by `date_built`
│   ├── date_built=2010/
│   ├── date_built=2011/
│   ├── ...
│   └── date_built=2017/
├── Home_Sales.ipynb              # Main analysis notebook
├── .gitignore
└── README.md                     # This file
```

---

## ✅ Conclusion

This project showcases how PySpark can be used to perform large-scale data analysis efficiently. By leveraging caching and Parquet partitioning, we significantly improved query performance and gained meaningful insights from the dataset. It's a solid demonstration of Spark's power for real-world data processing tasks.