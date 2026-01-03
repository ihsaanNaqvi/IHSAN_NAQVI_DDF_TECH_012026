# SQL Queries

## Sales by Category
SELECT category, SUM(price * quantity) AS revenue
FROM fact_sales
GROUP BY category;



## Revenue Over Time
SELECT order_date, SUM(price * quantity)
FROM fact_sales
GROUP BY order_date;


Q1 — Total Revenue by Category (BAR)

 
SELECT
    p.normalized_category,
    SUM(f.total_amount) AS total_revenue
FROM fact_sales_sql f
JOIN dim_product_sql p
    ON f.product_id = p.product_id
GROUP BY p.normalized_category
ORDER BY total_revenue DESC;

q1 = """
SELECT
    p.normalized_category,
    SUM(f.total_amount) AS total_revenue
FROM fact_sales_sql f
JOIN dim_product_sql p
    ON f.product_id = p.product_id
GROUP BY p.normalized_category
ORDER BY total_revenue DESC
"""
pysqldf(q1)
 Q2 — Revenue Over Time (LINE)
 
q2 = """
SELECT
    d.year,
    d.month,
    SUM(f.total_amount) AS monthly_revenue
FROM fact_sales_sql f
JOIN dim_date_sql d
    ON f.date_id = d.date_id
GROUP BY d.year, d.month
ORDER BY d.year, d.month
"""
pysqldf(q2)
 Q3 — Revenue by Region (MAP / BAR)
 
q3 = """
SELECT
    r.region,
    SUM(f.total_amount) AS region_revenue
FROM fact_sales_sql f
JOIN dim_region_sql r
    ON f.region_id = r.region_id
GROUP BY r.region
ORDER BY region_revenue DESC
"""
pysqldf(q3)
  Q4 — Premium vs Non-Premium Sales (PIE)
 
q4 = """
SELECT
    p.is_premium_product,
    SUM(f.total_amount) AS revenue
FROM fact_sales_sql f
JOIN dim_product_sql p
    ON f.product_id = p.product_id
GROUP BY p.is_premium_product
"""
pysqldf(q4)

  Q5 — Top 5 Products by Revenue (TABLE)
 
 
q5 = """
SELECT
    p.title,
    SUM(f.total_amount) AS product_revenue
FROM fact_sales_sql f
JOIN dim_product_sql p
    ON f.product_id = p.product_id
GROUP BY p.title
ORDER BY product_revenue DESC
LIMIT 5
"""
pysqldf(q5)
