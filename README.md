# 📊 TASK 6: Sales Trend Analysis Using Aggregations

## 🎯 Objective
To analyze **monthly revenue** and **order volume** using SQL aggregation techniques.

---

## 🛠️ Tools Used
- PostgreSQL / MySQL / SQLite  
- _(Tool I used: **PostgreSQL** / Replace with your actual tool)_

---

## 📁 Dataset Description
**Table Name:** `online_sales`  
Columns included:
- `order_date` – Date of the order  
- `amount` – Revenue for each order  
- `product_id` – ID of the product  
- `order_id` – Unique order identifier

---

## ✅ Task Steps
1. Extracted **year** and **month** from `order_date`.
2. Grouped the data by **year and month**.
3. Calculated:
   - `SUM(amount)` as total revenue.
   - `COUNT(DISTINCT order_id)` as order volume.
4. Used `ORDER BY` to sort the results.
5. Used `LIMIT` to fetch **top 3 months** by sales.

---

## 🧠 SQL Concepts Used
- `EXTRACT(MONTH FROM order_date)`
- `EXTRACT(YEAR FROM order_date)`
- `SUM()`
- `COUNT(DISTINCT ...)`
- `GROUP BY`
- `ORDER BY`
- `LIMIT`

---

## 💻 Sample SQL Query

```sql
SELECT 
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM 
    online_sales
GROUP BY 
    year, month
ORDER BY 
    total_revenue DESC
LIMIT 3;
