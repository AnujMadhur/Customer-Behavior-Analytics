# 🛍️ Customer Behavior Analytics Pipeline
### Python · MySQL · Power BI · SQL

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![MySQL](https://img.shields.io/badge/MySQL-8.0-orange?style=flat&logo=mysql)
![PowerBI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?style=flat&logo=powerbi)
![Status](https://img.shields.io/badge/Status-Completed-green?style=flat)

---

## 📌 Project Overview

This project analyzes **3,900+ retail customer records** to uncover shopping patterns, customer segments, and revenue insights. It covers a complete data analytics workflow — from raw CSV data all the way to an interactive Power BI dashboard.

The goal is to help a retail store answer real business questions like:
- Which customers are most valuable?
- Do subscribed customers spend more?
- Which products get the best ratings?
- Which age group contributes the most revenue?

---

## 🗂️ Project Structure

```
📁 customer-behavior-analytics/
 ├── 📓 Customer_Shopping_Behavior_Analysis.ipynb   → Data cleaning, feature engineering & MySQL loading
 ├── 📄 customer_shopping_behavior.csv              → Raw dataset (3,900 rows, 18 columns)
 ├── 📄 customer_behavior_sql_queries.sql           → 10 SQL queries answering business questions
 ├── 📊 customer_behavior_dashboard.pbix            → Interactive Power BI dashboard
 └── 📄 README.md
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Data cleaning and feature engineering |
| Pandas | Data manipulation and transformation |
| SQLAlchemy | Connecting Python to MySQL |
| MySQL | Storing and querying the cleaned data |
| MySQL Workbench | Running SQL queries visually |
| Power BI | Building interactive dashboards |
| Jupyter Notebook | Development environment |

---

## 📊 Dataset

- **Source:** Customer Shopping Behavior Dataset
- **Size:** 3,900 rows × 18 columns
- **Key Columns:** Customer ID, Age, Gender, Item Purchased, Category, Purchase Amount, Review Rating, Subscription Status, Discount Applied, Previous Purchases, Frequency of Purchases

---

## 🔧 What Was Done

### 1. Data Cleaning (Python)
- Handled missing values in Review Rating using **category-wise median imputation**
- Renamed all columns to snake_case for SQL compatibility
- Removed duplicate column (promo_code_used was identical to discount_applied)
- Standardized data types and formats

### 2. Feature Engineering (Python)
- Created **age_group** column — divided customers into Young Adult, Adult, Middle-aged, Senior using `pd.qcut`
- Created **purchase_frequency_days** — converted text frequency (Weekly, Monthly) into numeric days (7, 30)

### 3. Database Loading (Python → MySQL)
- Connected Python to MySQL using SQLAlchemy
- Loaded cleaned DataFrame into MySQL as the `customer` table

### 4. SQL Analysis (10 Queries)

| # | Business Question |
|---|------------------|
| Q1 | Total revenue by gender |
| Q2 | Discount users who spent above average |
| Q3 | Top 5 products by average review rating |
| Q4 | Average spend: Standard vs Express shipping |
| Q5 | Subscriber vs non-subscriber spend comparison |
| Q6 | Top 5 products with highest discount usage rate |
| Q7 | Customer segmentation — New, Returning, Loyal |
| Q8 | Top 3 products in each category |
| Q9 | Do repeat buyers subscribe more? |
| Q10 | Revenue contribution by age group |

### 5. Power BI Dashboard
- Connected Power BI to MySQL database
- Built interactive dashboard with slicers, bar charts, pie charts, and KPI cards
- Visualized revenue trends, customer segments, product performance, and discount impact

---

## 💡 Key Business Insights

- 📌 **Subscribed customers** spend significantly more on average than non-subscribers
- 📌 **Senior age group** contributes the highest total revenue despite being a smaller group
- 📌 **60%+** of customers who used discounts still spent above the average purchase amount
- 📌 Majority of customers fall in the **Returning** segment (2–10 previous purchases)
- 📌 Top-rated products are consistent across seasons and categories

---

## 🚀 How to Run This Project

### Prerequisites
```bash
pip install pandas numpy sqlalchemy pymysql jupyter
```

### Step 1 — Set Up MySQL
1. Install MySQL and create a database:
```sql
CREATE DATABASE customer_behavior;
```

### Step 2 — Run the Notebook
```bash
jupyter notebook
```
Open `Customer_Shopping_Behavior_Analysis.ipynb` and update the connection cell:
```python
engine = create_engine('mysql+pymysql://root:YOUR_PASSWORD@localhost/customer_behavior')
```
Run all cells — data will be loaded into MySQL automatically.

### Step 3 — Run SQL Queries
Open `customer_behavior_sql_queries.sql` in MySQL Workbench and execute all queries.

### Step 4 — Open Dashboard
Open `customer_behavior_dashboard.pbix` in Power BI Desktop.
Go to **Home → Refresh** to load your MySQL data.

---

## 📸 Dashboard Preview

> Open the `.pbix` file in Power BI Desktop to view the full interactive dashboard.

---

## 🤝 Connect With Me

Feel free to reach out if you have any questions or suggestions about this project!

---

⭐ **If you found this project helpful, please give it a star!**
