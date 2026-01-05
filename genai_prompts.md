# GenAI Prompts Documentation

## Context
These prompts were used to transform unstructured e-commerce product text
(title and description) into structured analytical features.
The outputs are used for data modeling, analytics, and dashboards.

All prompts were executed programmatically and are fully reproducible.

---

## Prompt 1 — Normalized Category

### Purpose
Standardize inconsistent product categories into a clean analytical taxonomy.

### Prompt
"""
You are a data analyst working with e-commerce data.
Normalize the following product category into a concise and standard retail category.
Return only the normalized category name.
"""

### Inputs
- product title
- product description
- raw category

### Output
- normalized_category (string)

---

## Prompt 2 — Product Tags Extraction

### Purpose
Generate structured keywords for analytical filtering and segmentation.

### Prompt
"""
Extract 3 to 5 concise analytical product tags from the following product title
and description. Tags should describe product type, material, or main features.
Return the result as a comma-separated list. Do not add explanations.
"""

### Inputs
- product title
- product description

### Output
- product_tags (comma-separated string)

---

## Prompt 3 — Product Summary

### Purpose
Create a short business-friendly product description for dashboards.

### Prompt
"""
Summarize the following product title and description in one clear sentence.
The summary must be suitable for a business analytics dashboard.
"""

### Inputs
- product title
- product description

### Output
- product_summary (string)

---

## Prompt 4 — Premium Product Classification

### Purpose
Classify products for pricing and segmentation analysis.

### Prompt
"""
Based on the product title, description, and price, determine whether this is a
premium product. Consider quality, materials, and positioning.
Return only one value: TRUE or FALSE.
"""

### Inputs
- product title
- product description
- product price

### Output
- is_premium_product (boolean)
