# Retail Sales SQL Analytics Project

## 1. Project Overview

This project uses SQL and PostgreSQL to analyze retail sales data and generate business insights that can support better decision-making.

The analysis focuses on customer purchasing behaviour, product performance, revenue generation, profitability, geographical sales distribution, customer segmentation and sales trends.

The project demonstrates how SQL can be used to extract, transform, analyze and interpret business data to solve real-world retail challenges.

## 2. Project Objectives

The main objectives are to:

- Analyze sales performance and revenue across product categories.
- Identify the highest and lowest-performing products.
- Understand customer purchasing patterns and spending behaviour.
- Evaluate revenue contribution across different cities.
- Analyze customer segments, including Retail, Corporate and VIP.
- Identify inactive customers and opportunities for customer retention.
- Measure monthly sales growth and seasonality.
- Generate actionable insights and recommendations for management.

## 3. Dataset Description

The project uses a simulated retail sales dataset containing two main tables.

### Customers Table

Contains customer demographic and registration information.

 Column | Description 

| customer_id | Unique customer identifier |
| customer_name | Customer's full name |
| gender | Customer gender |
| city | Customer's location |
| registration_date | Date the customer registered |
| customer_segment | Retail, Corporate or VIP |

### Orders Table

Contains retail transaction and sales information.

 Column | Description 
|
| order_id | Unique order identifier |
| customer_id | Customer who placed the order |
| order_date | Date the order was placed |
| product_name | Name of the purchased product |
| product_category | Product category |
| quantity | Number of units ordered |
| unit_price | Selling price per unit |
| cost_price | Cost price per unit |
| discount | Discount percentage |
| payment_method | Method used to pay |
| order_status | Order completion status |

**Dataset size:**
- 150 customers
- 800 orders

## 4. Tools and Technologies

- **PostgreSQL:** Database management and SQL querying.
- **SQL:** Data retrieval, cleaning, aggregation and analysis.
- **GitHub:**  project documentation.

## 5. Project Structure

```text
retail-sales-sql/
│
├── README.md
├── schema.sql
├── queries.sql
├── insights.md
│
└── screenshots/
    ├── 01_data_verification.png
    ├── 02_category_revenue.png
    ├── 03_city_revenue.png
    ├── 04_customer_segments.png
    └── 05_monthly_sales.png
```
## 6. Database Setup and Installation

Follow these steps to reproduce the analysis.

### Step 1: Install PostgreSQL

### Step 2: Create the Database

Open your PostgreSQL query editor and execute:

```sql
CREATE DATABASE retail_analytics;
```

Connect to the newly created `reretail_analytics` database before running the remaining scripts.

### Step 3: Create the Tables

This creates the customers and orders tables and establishes the relationship between them.

### Step 4: Import the Dataset

Execute the original customer and order insertion scripts in the following order:

1. `03_insert_customers.sql`
2. `04_insert_orders.sql`

Ensure that customer records are inserted before orders because the orders table references customer IDs.

### Step 5: Verify the Data

Run the verification queries to confirm that the records were successfully inserted.

```sql
SELECT COUNT(*) FROM customers;

SELECT COUNT(*) FROM orders;
```

Expected results:

- Customers: 150
- Orders: 800

## 7. SQL Analysis Performed

The project contains 46 SQL questions organized into different analytical sections.

 Section | Analysis 

| Section A | SQL fundamentals and data retrieval |
| Section B | Aggregations and sales calculations |
| Section C | Joins and customer analytics |
| Section D | Subqueries and Common Table Expressions (CTEs) |
| Section E | Window functions and advanced analysis |
| Section F | Business intelligence and reporting |


### Key SQL Concepts Applied

- SELECT, WHERE and ORDER BY
- DISTINCT and BETWEEN
- COUNT, SUM, AVG, MIN and MAX
- GROUP BY and HAVING
- INNER JOIN and LEFT JOIN
- Subqueries and CTEs
- CASE WHEN statements
- Window functions and ranking
- Views and stored functions
- Indexing and query performance analysis
- Date and time functions

## 8. Key Business Insights

The analysis produced several important findings:

1. **Product performance:** Mobile Phones generated the highest revenue, while Accessories recorded the strongest profit margin.
2. **Geographical performance:** Nairobi was the highest revenue-generating city, contributing approximately 39.67% of total completed-order revenue.
3. **Customer segmentation:** Retail customers generated the highest total revenue, while Corporate customers demonstrated stronger profit margins.
4. **Customer retention:** Approximately 43.33% of customers met the project's dormant-customer definition.
5. **Sales growth:** Revenue increased by approximately 20.33% between Q2 and Q3 2026.
6. **Customer value:** High-value customers contributed approximately 86.65% of completed-order revenue.

Further explanations, business implications and recommendations are documented in `insights.md`.

## 9. Revenue and Profit Calculations

Revenue is calculated after applying the discount:

```sql
quantity * unit_price * (1 - discount / 100.0)
```

Total cost is calculated as:

```sql
quantity * cost_price
```

Profit is calculated as:

```sql
Revenue - Cost
```

Profit margin is calculated as:

```sql
(Profit / Revenue) * 100
```

For revenue and profit analysis, only completed orders are included unless a question specifies otherwise.

## 10. Screenshots and Results

The `screenshots/` folder contains selected SQL query outputs demonstrating the analysis.

These include:

- Database verification results.

![Customers Overview](file:///c%3A/Users/LENOVO/Desktop/LUXDV/assg/sql/Week%2010%20Retail%20Sales%20%26%20Customer%20Intelligence%20Using%20PostgreSQL/screenshorts/1%20customres%20total.JPG)

![orders overview](file:///c%3A/Users/LENOVO/Desktop/LUXDV/assg/sql/Week%2010%20Retail%20Sales%20%26%20Customer%20Intelligence%20Using%20PostgreSQL/screenshorts/2orders%20total.JPG)

- Revenue by customer city.

![customer city vs Revenue](file:///c%3A/Users/LENOVO/Desktop/LUXDV/assg/sql/Week%2010%20Retail%20Sales%20%26%20Customer%20Intelligence%20Using%20PostgreSQL/screenshorts/City_revenue.JPG)


- Customer segmentation results.
![customer_segment vs revenue](file:///c%3A/Users/LENOVO/Desktop/LUXDV/assg/sql/Week%2010%20Retail%20Sales%20%26%20Customer%20Intelligence%20Using%20PostgreSQL/screenshorts/Customer_segment_revenue.JPG)

- Customer category vs Revenue.
![customer category vs revenue](file:///c%3A/Users/LENOVO/Desktop/LUXDV/assg/sql/Week%2010%20Retail%20Sales%20%26%20Customer%20Intelligence%20Using%20PostgreSQL/screenshorts/Category_revenue.JPG)


## 11. Recommendations

Based on the analysis, the following actions are recommended:

- Strengthen marketing and distribution for high-revenue product categories.
- Promote higher-margin products through product bundling and cross-selling.
- Expand customer acquisition in lower-performing cities.
- Introduce loyalty programmes to encourage repeat purchases.
- Develop targeted campaigns to reactivate dormant customers.
- Strengthen relationships with high-value and corporate customers.
- Monitor monthly sales performance to improve inventory and business planning.

## 12. Conclusion

This project demonstrates how SQL can transform raw retail transaction data into meaningful business insights.

Through data aggregation, joins, subqueries, CTEs and window functions, the analysis provides an understanding of sales performance, customer behaviour, product profitability and geographical revenue contribution.

The findings provide a foundation for data-driven decision-making and demonstrate practical SQL skills applicable to business intelligence, data analytics and reporting.

