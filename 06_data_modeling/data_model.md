# Data Modeling

Approach: Kimball Star Schema

Fact Table:
- fact_sales

Dimensions:
- dim_product
- dim_date
- dim_region

This model optimizes analytical queries and dashboard performance.
# Data Modeling

A star schema was implemented to support analytical workloads for an e-commerce platform.

## Fact Table
**fact_sales**
- Stores transactional metrics (quantity, revenue)
- Linked to product, date, and region dimensions

## Dimensions
- **dim_product**: product metadata enriched with GenAI features
- **dim_date**: calendar attributes for time-based analysis
- **dim_region**: geographic attributes

This model is optimized for BI queries, scalability, and easy integration with visualization tools.
