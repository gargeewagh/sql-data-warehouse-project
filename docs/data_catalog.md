# Data Catalog – Gold Layer

## Overview

The **Gold Layer** represents the business-ready data model designed to support reporting, analytics, and business intelligence. It consists of **dimension tables** and **fact tables** that organize data into a structured format for efficient analysis. :contentReference[oaicite:0]{index=0}

---

## Gold Layer Tables

### 1. `gold.dim_customers`

**Purpose**

Stores customer information enriched with demographic and geographic details for analytical reporting. :contentReference[oaicite:1]{index=1}

#### Columns

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| customer_key | INT | Surrogate key uniquely identifying each customer record. |
| customer_id | INT | Unique customer identifier. |
| customer_number | NVARCHAR(50) | Alphanumeric customer reference number. |
| first_name | NVARCHAR(50) | Customer's first name. |
| last_name | NVARCHAR(50) | Customer's last name. |
| country | NVARCHAR(50) | Country of residence. |
| marital_status | NVARCHAR(50) | Customer's marital status. |
| gender | NVARCHAR(50) | Customer's gender. |
| birthdate | DATE | Customer's date of birth. |
| create_date | DATE | Date the customer record was created. |

---

### 2. `gold.dim_products`

**Purpose**

Provides product information and attributes used for reporting and business analysis. :contentReference[oaicite:2]{index=2}

#### Columns

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| product_key | INT | Surrogate key for each product. |
| product_id | INT | Unique product identifier. |
| product_number | NVARCHAR(50) | Alphanumeric product code. |
| product_name | NVARCHAR(50) | Product name and details. |
| category_id | NVARCHAR(50) | Product category identifier. |
| category | NVARCHAR(50) | High-level product category. |
| subcategory | NVARCHAR(50) | Product subcategory. |
| maintenance_required | NVARCHAR(50) | Indicates if maintenance is required. |
| cost | INT | Product cost. |
| product_line | NVARCHAR(50) | Product line or series. |
| start_date | DATE | Product availability date. |

---

### 3. `gold.facts_sales`

**Purpose**

Stores transactional sales records used for business reporting and analytics. :contentReference[oaicite:3]{index=3}

#### Columns

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| order_number | NVARCHAR(50) | Unique sales order number. |
| product_key | INT | Foreign key referencing the product dimension. |
| customer_key | INT | Foreign key referencing the customer dimension. |
| order_date | DATE | Date the order was placed. |
| due_date | DATE | Payment due date. |
| sales_amount | INT | Total sales amount. |
| quantity | INT | Quantity sold. |
| price | INT | Price per unit. |

---

## Gold Layer Architecture

The Gold Layer follows a **Star Schema** consisting of:

- **Dimension Tables**
  - `gold.dim_customers`
  - `gold.dim_products`

- **Fact Table**
  - `gold.facts_sales`

The dimension tables provide descriptive business information, while the fact table stores transactional sales data linked through surrogate keys.

---

## Purpose of the Gold Layer

- Provides business-ready data for reporting.
- Supports dashboards and analytical queries.
- Improves query performance.
- Organizes data using a Star Schema.
- Enables efficient business intelligence and decision-making.

---

## Documentation

This repository includes the complete **Gold Layer Data Catalog** describing each table, column, data type, and business purpose. :contentReference[oaicite:4]{index=4}
