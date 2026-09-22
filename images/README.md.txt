# PLSQL Assignment One - Sunrise Supermarket

## Student Information

- **Name:** SHEMA Christian
- **Student ID:** 29799
- **DBMS:** Oracle Database 21c
- **Repository:** `assignment_1_shema-christian-29799`

---

## 1. Business Scenario

Sunrise Supermarket sells products to customers who place orders.
Each order can contain one or more products.

The purpose of this assignment is to use SQL to analyze customer
information, products, orders, and sales.

The assignment demonstrates the use of:

- INNER JOIN
- LEFT JOIN
- Common Table Expressions (CTEs)
- Window functions
- Aggregate functions
- Ranking
- Running totals
- Date calculations

---

## 2. Database Structure

The database contains four tables:

### Customers

The `customers` table stores information about supermarket customers.

Columns:

- `customer_id`
- `customer_name`
- `email`
- `city`

### Products

The `products` table stores information about products sold by the
supermarket.

Columns:

- `product_id`
- `product_name`
- `category`
- `price`

### Orders

The `orders` table stores customer orders.

Columns:

- `order_id`
- `customer_id`
- `order_date`

### Order Items

The `order_items` table stores the products and quantities included
in each order.

Columns:

- `order_item_id`
- `order_id`
- `product_id`
- `quantity`

---

## 3. Data Populated

The database was populated with:

- **6 customers**
- **10 products**
- **4 product categories**
- **15 orders**
- **30 order items**
- Orders were created across multiple dates.

The product categories include:

- Dairy
- Bakery
- Grains
- Beverages

---

# 4. JOIN Queries

## JOIN 1 - Orders and Customers

### Question

List every order with the customer's name, city, and order date.

### SQL Query

```sql
SELECT
    o.order_id,
    c.customer_name,
    c.city,
    o.order_date
FROM orders o
INNER JOIN customers c
    ON o.customer_id = c.customer_id
ORDER BY o.order_date;