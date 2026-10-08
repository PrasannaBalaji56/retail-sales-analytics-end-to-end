# 📊 Retail Sales Analytics – End-to-End Data Analytics Project

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![SQL](https://img.shields.io/badge/SQL-MySQL-orange?logo=mysql)
![Excel](https://img.shields.io/badge/Excel-Data%20Cleaning-green?logo=microsoftexcel)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?logo=powerbi)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E?logo=scikitlearn)
![GitHub](https://img.shields.io/badge/GitHub-Version%20Control-black?logo=github)

> **An end-to-end retail sales analytics project using Excel, SQL, Python, RFM Analysis, Machine Learning and Power BI.**

---

## 🖼️ Project Dashboard Preview

<!--
Place your Power BI dashboard screenshot at:
screenshots/dashboard.png

The image will automatically appear on GitHub.
-->

![Power BI Dashboard](screenshots/dashboard.png)

---

# 1. 📌 Project Overview

Retail businesses generate large amounts of transactional, customer, product and inventory data. However, raw data alone does not provide meaningful business insights.

This project builds a complete analytics pipeline that transforms raw retail transaction data into actionable business insights through:

- 🧹 Data cleaning and preprocessing
- 🗄️ Relational database management using SQL
- 🐍 Exploratory Data Analysis using Python
- 👥 RFM customer analysis
- 🤖 Customer segmentation
- 📦 Inventory and product performance analysis
- 📊 Interactive Power BI dashboards
- 💡 Business-focused insights and reporting

---

# 2. 🎯 Business Objectives

The main objectives of this project are:

1. Analyze sales performance across stores and staff.
2. Identify high-value customers and purchasing patterns.
3. Segment customers based on their purchasing behavior.
4. Analyze product performance and inventory levels.
5. Identify low-stock products.
6. Analyze staff performance.
7. Track sales trends over time.
8. Build an interactive management dashboard.

---

# 3. 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| 📗 Excel | Data cleaning and preprocessing |
| 🗄️ MySQL / SQL | Data storage, querying and transformation |
| 🐍 Python | Data analysis and exploratory analysis |
| 🐼 Pandas | Data manipulation |
| 🔢 NumPy | Numerical analysis |
| 📈 Matplotlib | Data visualization |
| 📊 Seaborn | Statistical visualization |
| 🤖 Scikit-learn | Machine Learning and clustering |
| 🎯 K-Means | Customer segmentation |
| 📊 Power BI | Interactive dashboards and reporting |
| 🌐 GitHub | Version control and project documentation |

---

# 4. 🔄 End-to-End Data Pipeline

```text
                    📦 Raw Retail Data
                            │
                            ▼
                    📗 Excel
              Data Cleaning & Preparation
                            │
                            ▼
                       📄 CSV Files
                            │
                            ▼
                     🗄️ MySQL
             Database Creation & SQL Analysis
                            │
                            ▼
                      🐍 Python
                EDA + RFM Customer Analysis
                            │
                            ▼
                  🤖 Machine Learning
                  Customer Segmentation
                            │
                            ▼
                         🗄️ SQL
                 Customer Segment Storage
                            │
                            ▼
                       📊 Power BI
              Interactive Dashboard & Insights
```

---

# 5. 📂 Dataset Structure

The retail dataset consists of multiple relational tables:

- `customers`
- `orders`
- `order_items`
- `products`
- `brands`
- `categories`
- `stocks`
- `stores`
- `staffs`

### 📋 Table Overview

| Table | Description |
|---|---|
| `customers` | Customer information and location |
| `orders` | Customer transaction/order information |
| `order_items` | Individual products purchased in each order |
| `products` | Product information |
| `brands` | Product brand information |
| `categories` | Product category information |
| `stocks` | Product inventory across stores |
| `stores` | Store information |
| `staffs` | Staff information |

---

# 6. 🧹 Phase 1 – Excel Data Cleaning & Preparation

Excel was used as the initial data preparation layer.

### 🔧 Data Preprocessing Tasks

- Standardized column names
- Removed duplicate records
- Handled missing values
- Converted data types
- Validated data consistency
- Created derived columns
- Used VLOOKUP/XLOOKUP for lookup operations
- Created pivot tables
- Identified pricing outliers
- Prepared cleaned CSV files for SQL import

### 🧮 Example Derived Metric

```text
Total Price = (List Price × Quantity) - Discount
```

> **Note:** This formula reflects the project documentation. If `Discount` is stored as a percentage, use `List Price × Quantity × (1 - Discount)` in the actual calculation.

The cleaned datasets were then prepared for database loading.

### 🖼️ Excel Data Cleaning Preview

![Excel Data Cleaning](screenshots/excel_cleaning.png)

---

# 7. 🗄️ Phase 2 – SQL Database Management & Analysis

The cleaned CSV files were imported into a relational SQL database.

### 🔧 SQL Tasks Performed

- Database and table creation
- Primary key relationships
- Foreign key relationships
- Data loading
- INNER JOIN operations
- Aggregations
- GROUP BY analysis
- Filtering
- Sorting
- Customer purchase analysis
- Store sales analysis
- Product performance analysis
- Staff performance analysis
- Inventory analysis

---

## 7.1 🏪 Total Sales by Store

Analyzed total revenue generated by each store.

This helps identify high-performing and low-performing stores.

---

## 7.2 🏆 Top Selling Products

Identified the highest-selling products based on quantity.

---

## 7.3 👥 Customer Purchase Summary

Calculated:

- Number of orders
- Total items purchased
- Total revenue

---

## 7.4 💰 Customer Spending Segmentation

Customers were categorized according to their total spending.

---

## 7.5 👨‍💼 Staff Performance

Analyzed revenue generated through orders handled by each staff member.

---

## 7.6 ⚠️ Stock Alert

Identified products with stock levels below the defined threshold.

### 🖼️ SQL / Database Preview

![SQL Analysis](screenshots/sql_analysis.png)

---

# 8. 🐍 Phase 3 – Python Data Analysis

Python was used for exploratory data analysis and customer analytics.

### 📚 Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

---

## 8.1 🔎 Exploratory Data Analysis

The analysis included:

- Dataset inspection
- Data type analysis
- Descriptive statistics
- Value distributions
- Sales analysis
- Customer analysis
- Product analysis
- Visualization

Common exploratory functions included:

```python
df.info()
df.describe()
df.value_counts()
```

### 🖼️ Python EDA Preview

![Python EDA](screenshots/python_eda.png)

---

# 9. 👥 RFM Customer Analysis

RFM analysis was performed to understand customer purchasing behavior.

RFM stands for:

- 🔵 **Recency**
- 🟢 **Frequency**
- 🟠 **Monetary**

---

## 9.1 🔵 Recency

Measures how recently a customer made a purchase.

```text
Recency = Days since customer's last purchase
```

A lower recency value generally indicates a more recent purchase.

---

## 9.2 🟢 Frequency

Measures how often a customer purchases.

```text
Frequency = Number of orders placed
```

---

## 9.3 🟠 Monetary

Measures the total amount spent by the customer.

```text
Monetary = Total customer purchase value
```

These metrics were combined to create customer-level behavioral features.

### 🖼️ RFM Analysis Preview

![RFM Analysis](screenshots/rfm_analysis.png)

---

# 10. 🤖 Customer Segmentation

Customer segmentation was performed using customer purchasing behavior and RFM characteristics.

### 🎯 Segmentation Approach

The project uses customer RFM characteristics to group customers into meaningful business segments.

Example business segments include:

- 🏆 Champions / High-Value Customers
- 💚 Loyal Customers
- 🆕 New Customers
- ⚠️ At-Risk Customers
- 👥 Others

The resulting segmentation data was stored in the SQL database as:

```text
customer_segments
```

### 🖼️ Customer Segmentation Preview

![Customer Segmentation](screenshots/customer_segmentation.png)

---

# 11. 📊 Phase 4 – Power BI Dashboard

Power BI was used to create an interactive Business Intelligence dashboard.

The dashboard combines sales, customer, product, inventory, store and staff information.

---

## 11.1 💵 Sales Overview

- Total Revenue
- Total Orders
- Monthly Sales Trend
- Sales Over Time
- Average Order Value

---

## 11.2 🛍️ Product Analysis

- Top Selling Products
- Product Revenue
- Product Category Performance
- Quantity Sold
- Highest Revenue Product

---

## 11.3 👥 Customer Analysis

- Customer Purchasing Patterns
- Customer Segments
- Segment Revenue
- Customer Distribution
- High-Value Customer Analysis

---

## 11.4 🏪 Store Analysis

- Store Performance
- Sales by Store
- Geographic Sales Distribution

---

## 11.5 📦 Inventory Analysis

- Stock Levels
- Low Stock Products
- Inventory Alerts
- Products Requiring Restocking

---

## 11.6 👨‍💼 Staff Performance

- Revenue by Staff
- Staff Sales Contribution
- Comparison of Staff Performance

---

# 12. 🎛️ Interactive Filters & Slicers

The Power BI dashboard includes interactive filters/slicers for:

- 📌 Order Status
- 🏷️ Product Category
- 🏪 Store
- 👥 Customer Segment

These filters allow management users to dynamically explore different parts of the business data.

### 🖼️ Interactive Dashboard

![Power BI Dashboard](screenshots/dashboard.png)

---

# 13. 📈 Key Business Questions Answered

## 💵 Sales

- What is the total revenue?
- How are sales changing over time?
- Which stores generate the highest revenue?
- Which products generate the most sales?
- What is the average order value?
- Which categories contribute the most revenue?

## 👥 Customers

- Who are the highest-value customers?
- How frequently do customers purchase?
- Which customers are at risk of becoming inactive?
- What are the major customer segments?
- Which segments generate the most revenue?

## 🛍️ Products

- Which products are selling the most?
- Which categories contribute the most revenue?
- Which products have low inventory?
- Which products generate the highest revenue?

## 🏪 Stores

- Which store generates the highest revenue?
- How does performance vary between stores?
- What is the geographic distribution of sales?

## 👨‍💼 Staff

- Which staff members generate the highest revenue?
- How does sales performance vary across staff?
- Which staff members contribute most to overall sales?

## 📦 Inventory

- Which products need restocking?
- Which stores have low-stock products?
- Which products have inventory alerts?

---

# 14. 📊 Key KPIs

The Power BI dashboard provides important business KPIs such as:

| KPI | Description |
|---|---|
| 💰 Total Revenue | Overall sales revenue |
| 🛒 Total Orders | Total number of orders |
| 📦 Total Quantity Sold | Total units sold |
| 💵 Average Order Value | Average revenue per order |
| 👥 Active Customers | Customers with purchase activity |
| 🏆 Top Selling Product | Product with highest sales quantity |
| 💰 Highest Revenue Product | Product generating the highest revenue |
| 📦 Low Stock Products | Products below stock threshold |

---

# 15. 🔗 Data Pipeline Integration

The project integrates multiple technologies into one complete analytics workflow.

```text
             ┌─────────────────────┐
             │   📦 Raw Dataset    │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │     📗 Excel       │
             │ Data Cleaning       │
             │ & Preparation       │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │      🗄️ SQL        │
             │ Data Storage &      │
             │ Business Queries    │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │     🐍 Python       │
             │ EDA + RFM Analysis  │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │ 👥 Customer         │
             │ Segmentation        │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │    📊 Power BI      │
             │ Interactive         │
             │ Dashboard           │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │ 💡 Business         │
             │ Insights            │
             └─────────────────────┘
```

---

# 16. 📁 Project Structure

```text
retail-sales-analytics-end-to-end/
│
├── README.md
├── .gitignore
│
├── data/
│   ├── raw/
│   └── cleaned/
│
├── excel/
│   └── Excel_cleaned.xlsx
│
├── sql/
│   ├── schema.sql
│   └── analysis_queries.sql
│
├── python/
│   └── retail_sales_analysis.ipynb
│
├── powerbi/
│   └── Retail_Sales_Dashboard.pbix
│
├── report/
│   └── Project_Report.pdf
│
├── presentation/
│   └── Final_Presentation.pptx
│
└── screenshots/
    ├── dashboard.png
    ├── excel_cleaning.png
    ├── sql_analysis.png
    ├── python_eda.png
    ├── rfm_analysis.png
    └── customer_segmentation.png
```

---

# 17. 📦 Project Deliverables

The project includes:

- 📗 Cleaned Excel datasets
- 🗄️ SQL database schema
- 🔎 SQL analytical queries
- 🐍 Python exploratory data analysis
- 👥 RFM customer analysis
- 🤖 Customer segmentation analysis
- 📊 Power BI dashboard
- 📄 Project report
- 🎤 Project presentation

---

# 18. 💡 Business Insights

The project provides a consolidated view of retail business performance.

It helps management understand:

- 📈 Overall sales performance
- 🏪 Store-level performance
- 🛍️ Product demand
- 👥 Customer purchasing behavior
- 💰 High-value customers
- 🎯 Customer segments
- 👨‍💼 Staff performance
- 📦 Inventory levels
- ⚠️ Low-stock products
- 💵 Revenue contribution across business dimensions

The analysis can support data-driven decisions related to:

- Sales strategy
- Customer engagement
- Product management
- Inventory planning
- Staff performance
- Business reporting

---

# 19. 🚀 How to Run the Project

## Step 1 – Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/retail-sales-analytics-end-to-end.git
```

Move into the project directory:

```bash
cd retail-sales-analytics-end-to-end
```

---

## Step 2 – Review the Excel Data

Navigate to:

```text
excel/
```

Review the cleaned and prepared datasets.

---

## Step 3 – Set Up the SQL Database

Navigate to:

```text
sql/
```

Run the database schema script first.

Then execute the required SQL queries from:

```text
analysis_queries.sql
```

---

## Step 4 – Run the Python Analysis

Navigate to:

```text
python/
```

Open:

```text
retail_sales_analysis.ipynb
```

Run the notebook using Jupyter Notebook, JupyterLab, or VS Code.

Install the required libraries if necessary:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn sqlalchemy pymysql
```

---

## Step 5 – Open the Power BI Dashboard

Navigate to:

```text
powerbi/
```

Open:

```text
Retail_Sales_Dashboard.pbix
```

If required, update the SQL database connection to match your local MySQL configuration.

---

# 20. 🖼️ Dashboard & Project Screenshots

### 📊 Power BI Dashboard

![Power BI Dashboard](screenshots/dashboard.png)

### 📗 Excel Data Cleaning

![Excel Data Cleaning](screenshots/excel_cleaning.png)

### 🗄️ SQL Analysis

![SQL Analysis](screenshots/sql_analysis.png)

### 🐍 Python EDA

![Python EDA](screenshots/python_eda.png)

### 👥 RFM Analysis

![RFM Analysis](screenshots/rfm_analysis.png)

### 🤖 Customer Segmentation

![Customer Segmentation](screenshots/customer_segmentation.png)

> **GitHub image setup:** save your screenshots inside the `screenshots/` folder using the exact filenames shown above. GitHub will automatically render them inside this README.

---

# 21. 🧠 Skills Demonstrated

## 📊 Data Analytics

- Data Cleaning
- Data Preprocessing
- Exploratory Data Analysis
- Business Analysis
- KPI Development
- Data Visualization

## 📗 Excel

- Data Cleaning
- VLOOKUP
- XLOOKUP
- Pivot Tables
- Data Validation
- Derived Columns
- Data Preparation

## 🗄️ SQL

- Database Design
- Relational Data Modeling
- Primary Keys
- Foreign Keys
- INNER JOIN
- GROUP BY
- Aggregations
- Filtering
- Sorting
- Business Analysis Queries

## 🐍 Python

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Data Transformation
- Exploratory Data Analysis

## 👥 Customer Analytics

- RFM Analysis
- Recency Analysis
- Frequency Analysis
- Monetary Analysis
- Customer Segmentation

## 📊 Power BI

- Data Modeling
- KPI Cards
- Interactive Dashboards
- Slicers
- Filters
- Sales Analysis
- Customer Analysis
- Product Analysis
- Inventory Analysis
- Staff Performance Analysis

---

# 22. 🎓 Project Context

This project was completed as part of Data Analytics training at **Vinsup Skill Academy**.

The project follows an end-to-end analytics workflow covering Excel, SQL, Python, customer analytics, and Power BI.

### 📌 Project Domain

```text
Retail
Sales Analytics
Customer Analytics
Inventory Analytics
Business Intelligence
```

---

# 23. 📜 Project Authorization

The project was created and authorized as part of the Vinsup Skill Academy project program.

### Project Created By

**M S Gaurav Kumar**  
Skill Mentor – Data Analytics  
Vinsup Skill Academy

### Project Approved By

**Pooranam Annamalai**  
Chief Business & Production Officer  
Vinsup Skill Academy

---

# 24. 👨‍💻 Author

## Prasanna Balaji M

**Data Analyst | Data Science Enthusiast**

### Technical Skills

```text
Python
SQL
Excel
Power BI
Pandas
NumPy
Matplotlib
Seaborn
Machine Learning
RFM Analysis
Data Analytics
```

---

# 25. 🔗 Connect With Me

### GitHub

https://github.com/PrasannaBalaji56/

---

# 26. ⭐ Conclusion

This project demonstrates a complete end-to-end retail analytics workflow, starting from raw data cleaning and preprocessing and progressing through SQL database management, Python-based analysis, RFM customer segmentation, and Power BI dashboard development.

The project demonstrates how multiple analytics tools can be integrated to transform raw transactional data into meaningful business insights and support data-driven decision-making.

---

## ⭐ If you find this project useful, consider giving the repository a star!

![GitHub stars](https://img.shields.io/github/stars/PrasannaBalaji56/retail-sales-analytics-end-to-end?style=social)
