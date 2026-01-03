# Data Dictionary

| Column       | Type   | Description |
|-------------|--------|-------------|
| product_id  | string | Unique product identifier |
| title       | string | Product title |
| description | string | Product description (unstructured) |
| category    | string | Product category |
| price       | float  | Unit price |
| quantity    | int    | Quantity sold |
| order_date  | date   | Order date |
| region      | string | Sales region |

## Data Lake Zones
- Raw: Original CSV
- Trusted: Cleaned and validated data
- Refined: Feature-enriched with GenAI
