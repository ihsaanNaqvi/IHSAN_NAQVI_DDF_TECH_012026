# Data Dictionary

| Column | Type | Description |
|------|------|-------------|
| product_id | string | Unique product identifier |
| title | string | Product title |
| description | string | Product description |
| category | string | Product category |
| price | float | Unit price |
| order_date | date | Order date |
| quantity | int | Units sold |
| region | string | Sales region |

## Data Lake Zones
- Raw: original CSV
- Trusted: cleaned & typed
- Refined: LLM-enriched features
