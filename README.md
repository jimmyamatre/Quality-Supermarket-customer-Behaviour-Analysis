# Quality-Supermarket-customer-Behaviour-Analysis
Data Analytics project showcasing Quality Supermarket customer behaviour using python, SQL and PowerBI
---

# 🛒 Quality Supermarket Data Analytics Project

## 📘 Project Overview

Quality Supermarket, one of Uganda’s leading retail chains, seeks to better understand its customers’ shopping behavior to **boost sales, enhance customer satisfaction, and ensure long-term loyalty**.

This data analytics project was conducted to uncover key insights into **customer purchasing patterns**, **product performance**, and **sales trends** across multiple channels (in-store and online). The analysis integrates **Python**, **MySQL**, and **Power BI** for end-to-end data processing, analysis, and visualization.

---

## 🎯 Objectives

* Identify factors influencing customer purchasing behavior.
* Analyze sales performance across product categories and customer demographics.
* Determine customer loyalty and repeat purchase patterns.
* Provide actionable insights to support marketing and inventory decisions.

---

## 🧩 Dataset Description

The dataset used in this project contains detailed transaction-level and customer-level data.

**Key features include:**

* `Customer_ID`: Unique identifier for each customer.
* `Gender`, `Age`, `Location`: Customer demographics.
* `Product_Category`: Product classification (e.g., Groceries, Beverages, Household Items, Electronics).
* `Product_Name`: Specific items purchased.
* `Quantity`: Number of units purchased.
* `Unit_Price`: Price per item.
* `Discount`: Discount applied per transaction.
* `Payment_Mode`: Cash, Mobile Money, Card, or Online payment.
* `Date`: Transaction date.
* `Channel`: Indicates whether the purchase was Online or In-Store.

---

## ⚙️ Tools & Technologies Used

| Tool                                            | Purpose                                                        |
| ----------------------------------------------- | -------------------------------------------------------------- |
| **Python (Pandas, NumPy, Matplotlib, Seaborn)** | Data import, cleaning, preprocessing, and exploratory analysis |
| **MySQL**                                       | Structured storage, advanced querying, and relational analysis |
| **Power BI**                                    | Dashboard creation, KPI visualization, and trend analysis      |

---

## ⚙️ Installation & Usage

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/quality-supermarket-analytics.git
cd quality-supermarket-analytics
```

### 2️⃣ Install Required Libraries

Ensure Python (≥3.8) is installed. Then run:

```bash
pip install -r requirements.txt
```

**Example contents of `requirements.txt`:**

```
pandas
numpy
matplotlib
seaborn
mysql-connector-python
sqlalchemy
```

### 3️⃣ Load the Dataset

Place the dataset (`quality_supermarket_sales.csv`) inside the `/data` folder.

Open the Jupyter notebook under `/notebooks` and run the cells step by step for data cleaning and analysis.

```bash
jupyter notebook notebooks/01_data_cleaning.ipynb
```

### 4️⃣ Load Data into MySQL

Use the connection script to import the cleaned dataset into MySQL:

```python
import mysql.connector
import pandas as pd

df = pd.read_csv('data/cleaned_quality_sales.csv')
conn = mysql.connector.connect(user='root', password='yourpassword', host='localhost', database='quality_supermarket')
cursor = conn.cursor()

for _, row in df.iterrows():
    cursor.execute("INSERT INTO sales_data VALUES (%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)", tuple(row))
conn.commit()
```

### 5️⃣ Connect Power BI to MySQL

* Open **Power BI Desktop**
* Go to **Home → Get Data → MySQL Database**
* Enter your database credentials
* Import the cleaned data and build visuals

---

## 🧹 Data Preparation & Cleaning

1. **Data Importation:**
   Dataset imported into Python using `pandas.read_csv()`

2. **Preliminary Exploration:**

   * Checked shape (`df.shape`)
   * Checked data types (`df.info()`)
   * Handled missing and duplicate values
   * Standardized formats for categorical data

3. **Feature Engineering:**

   * Created `Total_Sales` (`Quantity * Unit_Price`)
   * Added `Discounted_Price`, `Month`, and `Quarter` fields
   * Grouped customers by spending behavior

---

## 📊 Analysis & Insights

**Python & MySQL Analysis included:**

* Sales by product category and region
* Average purchase frequency per customer segment
* Revenue contribution by online vs. offline channels
* Peak sales months and seasonal variations
* Impact of discounts on total revenue

**Power BI Dashboard Visuals:**

* 💰 Revenue by Product Category
* 📦 Sales by Payment Mode & Channel
* 🧾 Top 10 Products by Sales Volume
* 👥 Customer Retention & Repeat Purchases
* 📈 Monthly and Quarterly Sales Trends
* 🏬 Revenue by Store Location

---

## 📈 Key Findings

* **Groceries & Household Items** generated **45% of total sales**, making them the most profitable categories.
* **Mobile Money & Card payments** dominated with **60% usage** among active customers.
* **Online sales** rose by **28% YoY**, highlighting a shift to digital retailing.
* **Age group 25–40 years** had the highest repeat purchase rate.
* **Discount promotions** increased monthly revenue by up to **15%** during festive periods.
* **Kampala and Wakiso branches** accounted for **over 60% of total revenue**.

---

## 💡 Recommendations

1. Expand **loyalty programs** targeting young repeat buyers.
2. Increase **online inventory** to meet e-commerce growth.
3. Run **personalized discount campaigns** based on past shopping history.
4. Promote **mobile money payments** to enhance convenience.
5. Continuously monitor **category performance** to balance stock and pricing strategies.

---

## 🧠 Conclusion

The analysis demonstrates how data-driven decision-making can significantly improve retail performance. Integrating **Python**, **MySQL**, and **Power BI** enabled a full analytics pipeline — from raw data to actionable business insights — that can help Quality Supermarket increase profitability and customer loyalty.

---

## 📂 Project Structure

```
├── data/
│   └── quality_supermarket_sales.csv
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_analysis.ipynb
├── sql/
│   └── queries.sql
├── visuals/
│   └── PowerBI_dashboard.pbix
├── README.md
└── requirements.txt
```

---

## 👨‍💻 Author

**Jimmy Amatre**
Deputy Director, Social Services – KCCA
📧 Email: [[your.email@example.com](mailto:your.email@example.com)]
💼 LinkedIn: [linkedin.com/in/jimmy-amatre](#)

---
