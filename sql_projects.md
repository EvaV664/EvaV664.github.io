---
layout: page
title: SQL Projects
permalink: /sql_projects/
---

## 📊 **#1 — SQL with Python: Data Science Salaries Analysis** → [📓 View Notebook](DataScience_Salaries.html)

In this project, I explored a 2025 dataset of global data science, AI, and machine learning jobs. Using **SQLite3** and **Pandas**, I ran SQL queries to uncover salary trends based on experience, job category, and more. I also visualized the results using **Seaborn** and **Matplotlib**.

### Example Query: 📊 Top 5 Most Common Job Titles

To explore job demand in the data industry, I queried the dataset to find the five most common job titles.

#### 🧠 SQL Query Used
```sql
SELECT job_title, COUNT(*) AS job_count
FROM DataScience_Salaries
GROUP BY job_title
ORDER BY COUNT(*) DESC
LIMIT 5;
```

#### 🛠️ How I Did It
1. I used a Python function called run_query() to execute the SQL statement and return the results as a Pandas DataFrame:
```df_top = run_query(query6, conn)```
2. Then, I used Seaborn (with Matplotlib) to visualize the data as a horizontal bar chart:
```plt.figure(figsize=(10, 6))
sns.barplot(x='job_count', y='job_title', data=df_top, palette='Blues_d')
plt.title('Top 5 Most Common Job Titles')
plt.xlabel('Number of Jobs')
plt.ylabel('Job Title')
plt.tight_layout()
plt.show()
```

#### Results & Interpretation
The plot showed that the most frequent role was Machine Learning Engineer (88 listings), followed by Data Scientist (78). Junior and Senior titles appeared less often, possibly due to inconsistent labeling or because many postings didn’t specify experience level. This suggests that Machine Learning Engineers and Data Scientists are in especially high demand across companies.


### Key highlights:
- Most common job titles in the industry
- Salary comparisons by experience level
- Identification of outliers and patterns using boxplots


## 📦 **#2 — SQL with Python: Bike Store Sales & Revenue Analysis** → [📓 View Notebook](Sales_Insights.html)


In this project, I used **SQLite**, **Pandas**, and **Python** to explore a retail dataset containing bike sales, orders, staff, and customer data. I connected to the database, created relational joins across five tables, and ran SQL queries to uncover business insights. Then, I visualized the results using **Matplotlib** and **Seaborn**.

---

### 💸 Example Query: Top 10 Customers by Total Spending

To understand which customers drove the most revenue, I joined the `customers`, `orders`, and `order_items` tables and calculated the total spending per customer.

#### 🧠 SQL Query Used
```sql
SELECT 
    customers.customer_id,
    customers.first_name,
    customers.last_name,
    SUM(order_items.quantity * order_items.list_price * (1 - order_items.discount)) AS total_spent
FROM customers
JOIN orders ON customers.customer_id = orders.customer_id
JOIN order_items ON orders.order_id = order_items.order_id
GROUP BY customers.customer_id, customers.first_name, customers.last_name
ORDER BY total_spent DESC
LIMIT 10;
```

#### 🛠️ How I Did It
1. I used a custom Python function run_query() to send SQL queries to the SQLite database and return results in a Pandas DataFrame:
```
df4 = run_query(query4, conn)
```
2. Then, I visualized the top customers using Seaborn:
```
plt.figure(figsize=(10, 6))
sns.barplot(x='total_spent', y='first_name', data=df4)
plt.title('Top 10 Customers by Total Spending')
plt.xlabel('Total Spent (USD)')
plt.ylabel('Customer')
plt.tight_layout()
plt.show()
```
#### Results & Interpretation
- The top customer, Sharyn Hopkins, spent over $34,800.
- All top 10 customers spent over $24,000.
- These insights could support VIP loyalty programs, targeted marketing, or priority service strategies.

🔗 **View the full notebooks here:**  
👉 [Open DataScience_Salaries HTML Report](DataScience_Salaries.html)
👉 [Open Sales Insights HTML Report](Sales_Insights.html)
---

🛠 Technologies used: `SQLite`, `pandas`, `seaborn`, `matplotlib`, `Jupyter Notebooks`

📁 Datasets: DataScience_Salaries.csv, stores.csv, customers.csv, staffs.csv, order_items.csv, orders.csv  
📅 Year: 2025  
