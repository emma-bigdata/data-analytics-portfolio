# data-analytics-portfolio
Business Analytics Project — PostgreSQL (Northwind Dataset)
📘 Overview

This project explores business performance using SQL in PostgreSQL.
The dataset (Northwind) includes orders, products, customers, and shippers.
I used SQL to extract insights on revenue, profit, and customer retention.

🧮 Key Analysis

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

--CUSTOMER RFM--

SELECT
	C.CUSTOMER_ID,
	C.COMPANY_NAME,
	MAX(O.ORDER_DATE) AS LAST_ORDER_DATE,
	COUNT(O.ORDER_ID) FREQUENCY,
	ROUND(
		SUM(OD.UNIT_PRICE * OD.QUANTITY * 1 - (OD.DISCOUNT))::NUMERIC,
		2
	) AS MONETARY_VALUE
FROM
	CUSTOMERS AS C
	JOIN ORDERS AS O ON C.CUSTOMER_ID = O.CUSTOMER_ID
	JOIN ORDER_DETAILS AS OD ON O.ORDER_ID = OD.ORDER_ID
GROUP BY
	C.CUSTOMER_ID,
	COMPANY_NAME
ORDER BY
	MONETARY_VALUE DESC;
    
