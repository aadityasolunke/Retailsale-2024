# Retail Sales Analysis (SQL + Power BI)

A data analysis project for understanding retail sales trends, top-performing categories, customer behavior, and regional performance.

---

## Objective

To analyze sales data using SQL and visualize insights using Power BI — helping the business identify revenue drivers, top customers, and monthly trends for better decision-making.

---

## Key Questions Answered

- Which product categories generate the most revenue?
- Who are the top-spending customers?
- Which region performs the best?
- What are the sales trends over time?

---

## Dataset Description

| File | Description |
|------|--------------|
| customers.csv | Customer info (id, name, city, region) |
| products.csv | Product details (id, name, category, price) |
| sales.csv | Transaction details (id, product_id, customer_id, quantity, sale_date) |
| category_revenue.csv | Aggregated revenue per category |
| monthly_revenue.csv | Revenue trends by month |
| region_revenue.csv | Revenue by region |
| top_products.csv | Top selling products (quantity + revenue) |
| top_customerspend.csv | Top customers by total spending |

---

## Tools & Tech Stack

- **MySQL Workbench** – data storage and queries  
- **Power BI** – data visualization and dashboard creation  
- **Excel / CSV** – data aggregation and export  


---

## Key Insights

- **Apparel & Sports** categories generated the highest revenue.  
- **West region** contributed ~30% of total revenue.  
- **Vikram Joshi** is the top customer (₹5,000 spent).  
- **Sales peaked in April**, followed by a gradual decline toward November.

---

## SQL Highlights

Example Query — Top 5 Categories by Revenue:
```sql
SELECT p.category, SUM(s.quantity * p.price) AS total_revenue
FROM sales s
JOIN products p ON s.product_id = p.product_id
GROUP BY p.category
ORDER BY total_revenue DESC
LIMIT 5;
