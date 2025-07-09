---
layout: page
title: SQL Projects
permalink: /sql_projects/
---

## 📊 SQL with Python: Data Science Salaries Analysis → [📓 View Notebook](DataScience_Salaries.html)

In this project, I explored a 2025 dataset of global data science, AI, and machine learning jobs. Using **SQLite3** and **Pandas**, I ran SQL queries to uncover salary trends based on experience, job category, and more. I also visualized the results using **Seaborn** and **Matplotlib**.

## Example Query: 📊 Top 5 Most Common Job Titles

To explore job demand in the data industry, I queried the dataset to find the five most common job titles.

### 🧠 SQL Query Used
```sql
SELECT job_title, COUNT(*) AS job_count
FROM DataScience_Salaries
GROUP BY job_title
ORDER BY COUNT(*) DESC
LIMIT 5;
```

### 🛠️ How I Did It
1. I used a Python function called run_query() to execute the SQL statement and return the results as a Pandas DataFrame:
df_top = run_query(query6, conn)
2. Then, I used Seaborn (with Matplotlib) to visualize the data as a horizontal bar chart:
plt.figure(figsize=(10, 6))
sns.barplot(x='job_count', y='job_title', data=df_top, palette='Blues_d')
plt.title('Top 5 Most Common Job Titles')
plt.xlabel('Number of Jobs')
plt.ylabel('Job Title')
plt.tight_layout()
plt.show()
3. Results & Interpretation
The plot showed that the most frequent role was Machine Learning Engineer (88 listings), followed by Data Scientist (78). Junior and Senior titles appeared less often, possibly due to inconsistent labeling or because many postings didn’t specify experience level. This suggests that Machine Learning Engineers and Data Scientists are in especially high demand across companies.


## Key highlights:
- Most common job titles in the industry
- Salary comparisons by experience level
- Identification of outliers and patterns using boxplots

🔗 **View the full notebook here:**  
👉 [Open DataScience_Salaries HTML Report](../SQL%20with%20Python%20Project%20-%20DataScience_Salaries.html)

---

🛠 Technologies used: `SQLite`, `pandas`, `seaborn`, `matplotlib`, `Jupyter Notebooks`

📁 Dataset: DataScience_Salaries.csv  
📅 Year: 2025  
