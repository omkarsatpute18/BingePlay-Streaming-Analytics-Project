# BingePlay — Streaming Analytics Project 📊

## 📌 Project Overview

BingePlay is a simulated Indian OTT streaming service analytics project developed as part of the Data Analytics & Data Science Track.

The goal of this project is to use MySQL and Python to answer 12 real-world business questions related to subscriptions, revenue, user engagement, content performance, upgrades, comeback behavior, and churn.

The project was completed using a Jupyter Notebook connected to a MySQL database through SQLAlchemy and PyMySQL.

---

## 🎯 Project Mission

The mission was to analyze BingePlay's streaming data and answer 12 business questions across three levels:

- Tier 1 — Foundations
- Tier 2 — Joins & Subqueries
- Tier 3 — Advanced SQL

The project also focuses on writing readable SQL and handling common analytical challenges such as NULL values, multiple subscription records, self-joins, and window functions.

---

## 📊 Dataset

The BingePlay database contains five main tables:

| Table | Rows | Description |
|---------|---------|-------------|
| users | 3,000 | User information and signup details |
| subscriptions | 4,497 | Subscription history |
| shows | 100 | Show and content information |
| watch_sessions | 100,351 | User viewing sessions |
| ratings | 5,000 | User ratings |

### Important Data Details

- BingePlay launched in India on 1 January 2024.
- Subscription plans:
  - Basic ₹199/month
  - Premium ₹399/month
  - Family ₹699/month
- Subscriptions can contain multiple records for the same user.
- watch_sessions.user_id contains NULL values.
- Shows have a min_plan column indicating the minimum subscription plan required to watch them.

---

## 🔎 Business Questions Solved

### Q1 — Active Revenue
- Calculated active subscriptions as of 30 June 2024.
- Calculated total monthly recurring revenue.

### Q2 — Signup Momentum
- Counted new user signups for each month from January to June 2024.
- Identified the month with the highest number of signups.

### Q3 — Device Analytics
- Calculated total sessions by device.
- Calculated total and average watch minutes.
- Calculated completion rates.

### Q4 — Rating Distribution
- Calculated rating counts and percentages for 1–5 stars.
- Calculated the percentage of ratings that were 4 or 5 stars.

### Q5 — Originals vs Acquired
- Compared BingePlay Originals with acquired content.
- Compared show count, IMDb ratings, and release year.

### Q6 — Binge Day Detection
- Identified days where a user watched the same show 5 or more times.
- Analyzed binge behavior during Q2 2024.

### Q7 — Q1 Signups Who Never Watched
- Identified users who signed up in Q1 but never watched a session.
- Correctly handled NULL values using LEFT JOIN and IS NULL.

### Q8 — Over-Paying Premium/Family Users
- Identified Premium/Family users whose watch history only contained Basic-tier content.
- Used NOT EXISTS for anti-existence analysis.

### Q9 — Upgrade Success Cohort
- Identified users who started with Basic and later upgraded.
- Calculated average days to first upgrade.

### Q10 — Cliffhanger Comebacks
- Identified users who returned to the same show within 1–7 days after an incomplete session.
- Used self-joins for behavioral analysis.

### Q11 — Consecutive-Week Engagement
- Identified users with 4+ consecutive weeks of activity.
- Solved a gaps-and-islands problem using window functions.

### Q12 — Churn Signal Detection
- Identified users whose watch time dropped by 50% or more from May to June.
- Used LAG(), CTEs, and advanced filtering.

---

## 🛠️ Technologies Used

- MySQL
- Python
- Pandas
- SQLAlchemy
- PyMySQL
- Jupyter Notebook

---

## 🧠 SQL Concepts Used

- SELECT
- WHERE
- GROUP BY
- HAVING
- COUNT()
- SUM()
- AVG()
- ROUND()
- CASE WHEN
- INNER JOIN
- LEFT JOIN
- NOT EXISTS
- Correlated Subqueries
- Self Joins
- Common Table Expressions (CTEs)
- ROW_NUMBER()
- LAG()
- Window Functions
- Date Functions
- Gaps and Islands Analysis
- NULL Handling

---

## 📁 Project Structure

BingePlay_Project/

├── bingeplay_setup.sql

├── bingeplay_omkar.ipynb

└── README.md

---

## 🔌 Database Connection

```python
import pandas as pd
from sqlalchemy import create_engine

engine = create_engine(
    "mysql+pymysql://root:YOUR_PASSWORD@localhost/bingeplay"
)
```

Replace YOUR_PASSWORD with your MySQL password.

---

## 🚀 How to Run the Project

### 1. Start MySQL Server

Make sure MySQL is running on your system.

### 2. Load Database

Execute:

```sql
SOURCE bingeplay_setup.sql;
```

### 3. Verify Tables

```sql
SELECT COUNT(*) FROM users;
SELECT COUNT(*) FROM subscriptions;
SELECT COUNT(*) FROM shows;
SELECT COUNT(*) FROM watch_sessions;
SELECT COUNT(*) FROM ratings;
```

### 4. Install Required Libraries

```bash
pip install pandas sqlalchemy pymysql jupyter
```

### 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
bingeplay_omkar.ipynb
```

### 6. Run All Cells

Execute all notebook cells from top to bottom.

---

## 📈 Key Learning Outcomes

Through this project, I gained practical experience in:

- Translating business questions into SQL queries
- Revenue and subscription analytics
- User engagement analysis
- Content performance measurement
- Churn detection techniques
- Handling NULL values correctly
- Writing complex SQL queries
- Working with CTEs and Window Functions
- Solving real-world business problems using data

---

## 👨‍💻 Author

**Omkar Satpute**

Electronics & Telecommunication Engineering Student

Aspiring Data Analyst | SQL Enthusiast | Python Learner

---

## ⭐ Skills Demonstrated

SQL • MySQL • Python • Pandas • SQLAlchemy • PyMySQL • Data Analytics • Business Analytics • Window Functions • CTEs • Jupyter Notebook
