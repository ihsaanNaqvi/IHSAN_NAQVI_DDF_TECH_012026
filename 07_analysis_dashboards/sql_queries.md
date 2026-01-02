# SQL Queries

## Sales by Category
SELECT category, SUM(price * quantity) AS revenue
FROM fact_sales
GROUP BY category;

## Revenue Over Time
SELECT order_date, SUM(price * quantity)
FROM fact_sales
GROUP BY order_date;
