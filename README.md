# data-analytics-portfolio
Business Analytics Project — PostgreSQL (Northwind Dataset)
📘 Overview

This project explores business performance using SQL in PostgreSQL.
The dataset (Northwind) includes orders, products, customers, and shippers.
I used SQL to extract insights on revenue, profit, and customer retention.

🧮 Key Analyses

Monthly Revenue Trends

Year-over-Year Revenue Growth

Top 10 Products by Revenue

Profit by Category

Repeat Customer Rate

Average Order Value (AOV)

🧠 Tools & Skills Used

PostgreSQL (SQL Queries, Joins, CTEs, Window Functions)

Power BI (for visualizations)

Excel (for data review)

📊 Sample SQL Snippet
SELECT 
    DATE_TRUNC('month', o.orderdate) AS month,
    SUM(od.unitprice * od.quantity * (1 - od.discount)) AS total_revenue
FROM orders o
JOIN order_details od ON o.orderid = od.orderid
GROUP BY month
ORDER BY month;

📈 Insights

Revenue showed steady growth across months.

Beverages category produced the highest profit margin.

43% of customers made repeat purchases — a sign of strong loyalty.
