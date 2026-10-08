# 📊 Retail Sales Analytics — End-to-End Data Analytics Project

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![MySQL](https://img.shields.io/badge/MySQL-Database-orange?logo=mysql)
![Excel](https://img.shields.io/badge/Excel-Data%20Cleaning-green?logo=microsoftexcel)
![Power%20BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?logo=powerbi)
![Pandas](https://img.shields.io/badge/Pandas-Analysis-150458?logo=pandas)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E?logo=scikitlearn)
![GitHub](https://img.shields.io/badge/GitHub-Version%20Control-black?logo=github)

> **A complete retail analytics workflow combining Excel, MySQL, Python, RFM Customer Segmentation and Power BI to turn transactional data into business insights.**

---

## 🖼️ Project at a Glance

This project covers the complete analytics lifecycle:

**Raw Data → Excel Cleaning → MySQL Database → SQL Analysis → Python EDA → RFM Analysis → Customer Segmentation → Power BI Reporting**

### ⭐ Dashboard Preview

![Sales & Business Performance](screenshots/01_sales_business_performance.png)

![Product Analysis](screenshots/02_product_analysis.png)

![Customer & Staff Analysis](screenshots/03_customer_staff_analysis.png)

---

# 1. 📌 Project Overview

Retail businesses generate large volumes of customer, order, product, store, staff and inventory data. The purpose of this project is to convert that raw operational data into structured analysis and management-level insights.

The project demonstrates an end-to-end workflow using multiple analytics tools:

- 🧹 Excel for data cleaning and preparation
- 🗄️ MySQL for relational data storage and SQL analysis
- 🐍 Python/Pandas for exploratory data analysis
- 👥 RFM for customer behavior analysis
- 🎯 Rule-based customer segmentation
- 📊 Power BI for interactive reporting
- 🧠 Business questions and KPI analysis

---

# 2. 🎯 Business Objectives

The project aims to:

1. Analyze overall retail sales performance.
2. Compare store-level sales performance.
3. Identify top-performing products.
4. Analyze customer purchasing behavior.
5. Identify high-value and at-risk customers.
6. Perform RFM customer segmentation.
7. Analyze staff sales contribution.
8. Monitor inventory and low-stock products.
9. Build interactive Power BI dashboards.
10. Return analytical customer segments to MySQL for reuse in reporting.

---

# 3. 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| 📗 **Excel** | Data cleaning, lookup operations, pivot analysis and preparation |
| 🗄️ **MySQL** | Relational database, data storage and SQL analysis |
| 🐍 **Python** | Data analysis and customer analytics |
| 🐼 **Pandas** | DataFrames, transformations and RFM calculations |
| 🔢 **NumPy** | Numerical operations |
| 📈 **Matplotlib** | Exploratory visualizations |
| 📊 **Seaborn** | Statistical visualization |
| 🤖 **Scikit-learn** | Available for analytical/ML extensions |
| 📊 **Power BI** | Interactive dashboards and business reporting |
| 🐙 **Git/GitHub** | Version control and project presentation |

> **Implementation note:** The supplied RFM workflow uses **quantile-based RFM scoring and explicit rule-based segmentation**. It does not require a K-Means model for the final customer segment labels.

---

# 4. 🔄 End-to-End Workflow

```text
                 📦 RAW RETAIL DATA
                         │
                         ▼
                📗 EXCEL CLEANING
             Cleaning + Validation
                         │
                         ▼
                  📄 CLEAN DATA
                         │
                         ▼
                   🗄️ MYSQL
             Database + SQL Analysis
                         │
                         ▼
                   🐍 PYTHON
              EDA + Data Preparation
                         │
                         ▼
                   👥 RFM ANALYSIS
          Recency + Frequency + Monetary
                         │
                         ▼
                  🎯 RFM SCORING
                     Scores 1–5
                         │
                         ▼
             👤 CUSTOMER SEGMENTATION
                         │
                         ▼
                🗄️ MYSQL EXPORT
              customer_segments
                         │
                         ▼
                  📊 POWER BI
          Dashboard + Business Insights
```

The RFM report documents the same core sequence as:

**DATA → PREPARE → RFM → SCORE → SEGMENT → STORE**.

---

# 5. 📂 Dataset Structure

The project uses a relational retail database containing:

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
| `products` | Product master information |
| `brands` | Product brand information |
| `categories` | Product category information |
| `stocks` | Product inventory by store |
| `stores` | Store information |
| `staffs` | Staff information |

---

# 6. 🧹 Phase 1 — Excel Data Cleaning

Excel was used as the initial data preparation layer.

### 🔧 Tasks Performed

- Standardized column names
- Removed duplicate records
- Handled missing values
- Converted data types
- Validated data consistency
- Created derived columns
- Used VLOOKUP/XLOOKUP
- Created pivot tables
- Investigated pricing values/outliers
- Prepared cleaned data for SQL import

### 🧮 Example Calculation

```text
Total Price = (List Price × Quantity) - Discount
```

> If `Discount` is stored as a percentage rather than an absolute amount, the corresponding calculation should be `List Price × Quantity × (1 - Discount)`.

### 🖼️ Excel Preview

![Excel Data Cleaning](screenshots/excel_cleaning.png)

---

# 7. 🗄️ Phase 2 — MySQL Database & SQL Analysis

The cleaned datasets were loaded into a relational MySQL database.

### 🔧 SQL Work Performed

- Database creation
- Table creation
- Primary keys
- Foreign keys
- Data loading
- Relational joins
- Aggregations
- `GROUP BY`
- Filtering
- Sorting
- Customer purchase analysis
- Store sales analysis
- Product performance
- Staff performance
- Inventory analysis

### 🔗 Important Relationships

The RFM workflow joins:

```text
orders.order_id = order_items.order_id
```

This combines customer/order-date information from `orders` with transaction-value information from `order_items`.

### 🗺️ EER Diagram

![Database EER Diagram](screenshots/04_eer_diagram.png)

The EER diagram shows the relational structure connecting customers, orders, products, stores, staff, brands, categories, stocks and order items.

### 🖼️ SQL / Database Preview

![SQL Analysis](screenshots/sql_analysis.png)

---

# 8. 🐍 Phase 3 — Python Exploratory Data Analysis

Python and Pandas were used to load data from MySQL and perform exploratory analysis.

### 📚 Main Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sqlalchemy import create_engine
```

### 🔎 EDA Activities

- Dataset inspection
- Data type checking
- Descriptive statistics
- Frequency analysis
- Order distribution
- Quantity distribution
- Basic visualizations
- Data preparation for RFM

Common checks:

```python
orders.info()
order_items.info()
customers.info()

orders.describe()
order_items.describe()

orders["store_id"].value_counts()
```

### 🖼️ Python EDA Preview

![Python EDA](screenshots/python_eda.png)

---

# 9. 👥 Phase 4 — RFM Customer Analysis

RFM analysis converts transaction history into three customer-behavior dimensions:

### 🔵 Recency

How recently did the customer purchase?

```text
Recency = Analysis Date - Customer's Latest Order Date
```

Lower Recency is better because fewer days means a more recent purchase.

### 🟢 Frequency

How many distinct orders did the customer make?

```text
Frequency = Number of Unique Order IDs
```

`nunique()` is used because one order can contain multiple item rows.

### 🟠 Monetary

How much did the customer spend?

```text
Monetary = Sum of Total Purchase Value
```

The RFM report records the project analysis date as **2018-12-29**, based on the latest transaction date plus one day.

---

# 10. 📊 RFM Scoring

Raw RFM values use different units, so each metric is converted into a score from **1 to 5** using quantile-based grouping.

### 🔵 Recency Score

```python
rfm["R_score"] = pd.qcut(
    rfm["Recency"],
    5,
    labels=[5, 4, 3, 2, 1]
)
```

The labels are reversed because lower Recency is better.

### 🟢 Frequency Score

```python
rfm["F_score"] = pd.qcut(
    rfm["Frequency"].rank(method="first"),
    5,
    labels=[1, 2, 3, 4, 5]
)
```

Higher Frequency receives a higher score.

### 🟠 Monetary Score

```python
rfm["M_score"] = pd.qcut(
    rfm["Monetary"].rank(method="first"),
    5,
    labels=[1, 2, 3, 4, 5]
)
```

Higher Monetary value receives a higher score.

### 🔢 Combined RFM Score

```text
RFM_score = R Score + F Score + M Score
```

Example:

```text
555
554
552
234
111
```

`555` represents a customer in the highest scoring group across Recency, Frequency and Monetary. It is **not** 555 purchases or a currency amount.

### 🖼️ RFM Scoring Report

![RFM Scoring](screenshots/rfm_report/03_rfm_scoring.png)

---

# 11. 🎯 Customer Segmentation

After scoring, explicit business rules convert RFM scores into readable customer segments.

### 🏆 Champions

```text
R >= 4 AND F >= 4 AND M >= 4
```

Strong across all three RFM dimensions.

### 💚 Loyal Customers

```text
R >= 3 AND F >= 3
```

Reasonably recent and frequent customers.

### 🆕 New Customers

```text
R >= 4 AND F <= 2
```

Recent customers who have not yet purchased frequently.

### ⚠️ At Risk

```text
R <= 2 AND F >= 3
```

Historically frequent customers who are no longer recent.

### 👥 Others

Customers who do not meet the previous rules.

> These thresholds are **project-specific rules**, not universal industry standards.

### 🖼️ Segmentation Rules

![RFM Segmentation Rules](screenshots/rfm_report/04_rfm_segmentation_rules.png)

---

# 12. 📈 Actual RFM Segmentation Result

The final project output contains **1,445 customers**.

| Segment | Customers |
|---|---:|
| 👥 Others | 392 |
| 💚 Loyal Customers | 363 |
| ⚠️ At Risk | 326 |
| 🆕 New Customers | 186 |
| 🏆 Champions | 178 |
| **Total** | **1,445** |

The segment counts add up to the full 1,445-customer population, providing an important validation check.

### 🖼️ Final RFM Output

![Final RFM Output](screenshots/rfm_report/05_rfm_final_output.png)

---

# 13. 🗄️ Exporting Customer Segments Back to MySQL

The final RFM DataFrame is exported to MySQL as:

```text
customer_segments
```

The resulting table contains:

```text
customer_id
Recency
Frequency
Monetary
RFM_score
segment
```

Example:

```python
rfm.to_sql(
    "customer_segments",
    con=engine,
    if_exists="replace",
    index=True
)
```

The table can then be reused for SQL reporting and Power BI analysis.

---

# 14. 📊 Phase 5 — Power BI Dashboard

Power BI was used to create three analytical dashboard pages.

---

## 14.1 💰 Sales & Business Performance

The first page provides an overall sales view.

### KPIs

- Total Sales
- Total Quantity Sold
- Average Order Value
- Total Orders

### Visuals

- Sales by order date
- Monthly sales
- Sales by product
- Sales by staff
- Month slicer
- Customer segment slicer
- Store slicer

![Sales & Business Performance](screenshots/01_sales_business_performance.png)

---

## 14.2 🛍️ Product Analysis Report

The second page focuses on products and inventory.

### KPIs

- Total Products
- Highest Revenue Product
- Highest Sold Product

### Visuals

- Top 10 products by sales
- Sales by state/store
- Product quantity
- Stock status
- Store-level quantity distribution
- Month filter
- Stock-status filter

![Product Analysis](screenshots/02_product_analysis.png)

---

## 14.3 👥 Customer & Staff Analysis

The third page focuses on customer segmentation and staff performance.

### KPIs

- Customer Count
- Total Orders
- Total Staff

### Visuals

- Customer segmentation
- Sales by customer segment
- Sales by first name
- Sales by staff
- Segment filter
- Month filter

![Customer & Staff Analysis](screenshots/03_customer_staff_analysis.png)

---

# 15. 🎨 Dashboard Presentation

The original dashboard screenshots were retained as the source visuals, but the README versions have been **visually polished for GitHub presentation** with:

- ✨ Consistent framing
- 🖼️ Clean presentation cards
- 🟡 Consistent accent styling
- 📐 Consistent spacing
- 🔲 Rounded presentation borders
- 🏷️ Clear image titles
- 📱 Better readability when viewed in the repository

The underlying dashboard data and visuals are not altered; only the README presentation images are enhanced.

---

# 16. 🗺️ Database EER Diagram

The database structure is represented through an Entity Relationship Diagram.

![EER Diagram](screenshots/04_eer_diagram.png)

### Main entities represented

```text
customers
orders
order_items
products
brands
categories
stocks
stores
staffs
```

The diagram illustrates the relational connections used to support the retail analytics workflow.

---

# 17. 📚 RFM Learning / Documentation

A complete RFM guide was created alongside the project to explain:

- MySQL → Pandas connection
- Loading SQL tables
- EDA
- Merging `orders` and `order_items`
- Date conversion
- Analysis date
- Recency calculation
- Frequency calculation
- Monetary calculation
- RFM scoring
- Combined RFM score
- Customer segmentation
- Validation
- Export back to MySQL
- Interview explanation

### 📖 RFM Report Images

#### Roadmap

![RFM Roadmap](screenshots/rfm_report/01_rfm_roadmap.png)

#### Date Handling

![RFM Date Handling](screenshots/rfm_report/02_rfm_date_handling.png)

#### Scoring

![RFM Scoring](screenshots/rfm_report/03_rfm_scoring.png)

#### Segmentation

![RFM Segmentation](screenshots/rfm_report/04_rfm_segmentation_rules.png)

#### Final Output

![RFM Final Output](screenshots/rfm_report/05_rfm_final_output.png)

#### Validation & Interview Explanation

![RFM Validation](screenshots/rfm_report/06_rfm_validation_interview.png)

📄 The complete RFM guide is also included in:

```text
docs/RFM_Customer_Segmentation_Full_Guide.pdf
```

---

# 18. 📈 Key Business Questions Answered

## 💵 Sales

- What is the total sales value?
- How do sales change over time?
- Which stores generate the highest sales?
- Which products generate the most sales?
- What is the average order value?
- Which months contribute the most sales?

## 👥 Customers

- Who are the high-value customers?
- How recently did customers purchase?
- How frequently do customers purchase?
- How much do customers spend?
- Which customers are at risk?
- What are the major customer segments?
- Which segment generates the highest revenue?

## 🛍️ Products

- Which products sell the most?
- Which products generate the highest revenue?
- Which products have low stock?
- Which categories/products contribute strongly to sales?

## 🏪 Stores

- Which stores perform best?
- How does quantity sold vary by store?
- How does revenue vary across stores?

## 👨‍💼 Staff

- Which staff members contribute the most revenue?
- How does staff performance vary?

## 📦 Inventory

- Which products are low in stock?
- Which stores contain low-stock products?
- Which products may need restocking?

---

# 19. 📊 Key KPIs

| KPI | Business Meaning |
|---|---|
| 💰 Total Sales | Overall sales value |
| 🛒 Total Orders | Number of customer orders |
| 📦 Total Quantity Sold | Units sold |
| 💵 Average Order Value | Average value per order |
| 🛍️ Total Products | Number of products in analysis |
| 👥 Customer Count | Number of customers analyzed |
| 👨‍💼 Total Staff | Number of staff members |
| ⚠️ Low Stock | Products below the defined stock threshold |

---

# 20. 🧠 Key Analytical Decisions

### Why merge `orders` and `order_items`?

Customer identity and order date are stored in `orders`, while product quantity and transaction value are stored in `order_items`.

### Why use `nunique()` for Frequency?

One order can contain multiple item rows. Counting rows would overstate order frequency.

### Why reverse Recency scoring?

Lower Recency means a more recent purchase, so the most recent customers receive the highest Recency score.

### Why use `qcut()`?

It creates five relative customer groups, allowing the project to compare customers consistently across R, F and M.

### Why use `rank(method="first")`?

Frequency and Monetary can contain repeated values. Ranking first gives `qcut()` a unique ordering when creating five groups.

### Why export the result to SQL?

The segmented customer table can be reused for dashboards, reporting and further SQL analysis.

---

# 21. 📁 Recommended GitHub Repository Structure

```text
retail-sales-analytics/
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
├── docs/
│   └── RFM_Customer_Segmentation_Full_Guide.pdf
│
├── report/
│   └── Project_Report.pdf
│
├── presentation/
│   └── Final_Presentation.pptx
│
└── screenshots/
    ├── 01_sales_business_performance.png
    ├── 02_product_analysis.png
    ├── 03_customer_staff_analysis.png
    ├── 04_eer_diagram.png
    ├── excel_cleaning.png
    ├── sql_analysis.png
    ├── python_eda.png
    │
    └── rfm_report/
        ├── 01_rfm_roadmap.png
        ├── 02_rfm_date_handling.png
        ├── 03_rfm_scoring.png
        ├── 04_rfm_segmentation_rules.png
        ├── 05_rfm_final_output.png
        └── 06_rfm_validation_interview.png
```

---

# 22. 🚀 How to Run the Project

## Step 1 — Clone the Repository

```bash
git clone https://github.com/PrasannaBalaji56/retail-sales-analytics.git
cd retail-sales-analytics
```

## Step 2 — Prepare the Database

Create the MySQL database and tables using the SQL scripts.

```text
sql/schema.sql
```

Load the cleaned data into the corresponding tables.

## Step 3 — Run SQL Analysis

Execute:

```text
sql/analysis_queries.sql
```

## Step 4 — Run Python

Open:

```text
python/retail_sales_analysis.ipynb
```

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn sqlalchemy pymysql scikit-learn
```

Update the local MySQL connection credentials before running database-dependent cells.

## Step 5 — Run RFM Analysis

The Python workflow:

```text
MySQL
  ↓
Pandas
  ↓
orders + order_items
  ↓
RFM metrics
  ↓
RFM scores
  ↓
Customer segments
  ↓
customer_segments
```

## Step 6 — Open Power BI

Open:

```text
powerbi/Retail_Sales_Dashboard.pbix
```

Update the MySQL connection if required.

---

# 23. 🧪 Validation

The project includes validation checks for:

- Data types
- Missing values
- Date conversion
- Latest transaction date
- Recency values
- Frequency distribution
- Monetary values
- RFM score distribution
- Segment counts
- SQL export

### RFM Validation

The project produced:

```text
1,445 customers
289 customers per R score
289 customers per M score
```

The final segment counts sum to:

```text
1,445
```

This confirms that all customers were retained through the segmentation step.

---

# 24. 🧠 Skills Demonstrated

### 📊 Data Analytics

- Data Cleaning
- Data Preprocessing
- Exploratory Data Analysis
- Business Analysis
- KPI Analysis
- Data Visualization

### 📗 Excel

- VLOOKUP
- XLOOKUP
- Pivot Tables
- Data Cleaning
- Derived Columns
- Data Validation

### 🗄️ SQL

- Database Design
- Relational Data Modeling
- Primary Keys
- Foreign Keys
- INNER JOIN
- GROUP BY
- Aggregations
- Filtering
- Sorting
- Business Analysis

### 🐍 Python

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Data Transformation
- Exploratory Data Analysis

### 👥 Customer Analytics

- RFM Analysis
- Recency
- Frequency
- Monetary
- Quantile Scoring
- Customer Segmentation

### 📊 Power BI

- Data Modeling
- KPI Cards
- Interactive Dashboards
- Slicers
- Filters
- Sales Analysis
- Product Analysis
- Customer Analysis
- Inventory Analysis
- Staff Analysis

---

# 25. 🎓 Project Context

This project was completed as part of Data Analytics training at **Vinsup Skill Academy**.

The project follows an end-to-end analytics workflow covering Excel, SQL, Python, RFM customer analytics and Power BI.

### 📌 Domain

```text
Retail
Sales Analytics
Customer Analytics
Inventory Analytics
Business Intelligence
```

---

# 26. 👨‍💻 Author

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

### 🔗 GitHub

https://github.com/PrasannaBalaji56/

---

# 27. 📜 Project Authorization

The project documentation identifies the project as part of the Vinsup Skill Academy program.

**Project Created By**

M S Gaurav Kumar  
Skill Mentor – Data Analytics  
Vinsup Skill Academy

**Project Approved By**

Pooranam Annamalai  
Chief Business & Production Officer  
Vinsup Skill Academy

---

# 28. 💼 Interview Explanation

A concise way to explain the project:

> “I worked on an end-to-end retail analytics project where I cleaned and prepared data using Excel, loaded it into a MySQL relational database, and performed SQL-based business analysis. I then connected MySQL to Python using SQLAlchemy and PyMySQL, loaded orders, order items and customer data into Pandas, and performed EDA. For customer analytics, I calculated Recency, Frequency and Monetary metrics, converted them into five quantile-based scores, created rule-based customer segments, and exported the final customer segmentation back to MySQL. Finally, I used Power BI to build interactive dashboards covering sales, products, customers, stores, staff and inventory.”

---

# 29. ⭐ Conclusion

This project demonstrates how raw retail data can be transformed into meaningful business intelligence through a complete analytics pipeline.

```text
📦 DATA
   ↓
🧹 CLEAN
   ↓
🗄️ STORE
   ↓
🔎 ANALYZE
   ↓
👥 SEGMENT
   ↓
📊 VISUALIZE
   ↓
💡 DECIDE
```

The project combines technical data skills with business-oriented analysis and demonstrates the ability to work across **Excel → SQL → Python → RFM → Power BI**.

---

## ⭐ If you find this project useful, consider giving the repository a star!

![GitHub Stars](https://img.shields.io/github/stars/PrasannaBalaji56/retail-sales-analytics?style=social)
