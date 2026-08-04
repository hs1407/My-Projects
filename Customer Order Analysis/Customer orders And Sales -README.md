# Customer Orders and Sales Analysis Using SQL

## Project Overview

This project analyzes customer orders and sales transactions from January and February 2019. The analysis uses SQL to validate order records, connect customer accounts with purchases, measure revenue and product performance, and explore purchasing patterns across dates and locations.

The goal is to transform raw transactional data into useful business information that can support product, sales, inventory, and marketing decisions.

## Business Objectives

- Validate order records and remove invalid header rows from the analysis.
- Measure total orders, units sold, revenue, and average transaction value.
- Identify high-performing and low-priced products.
- Compare product demand across cities and specific store locations.
- Analyze purchasing activity by date and time.
- Connect sales transactions with customer account information.

## Dataset

The project uses three tables from the `BIT_DB` database:

| Table | Description | Main Fields |
| --- | --- | --- |
| `customers` | Connects customer accounts with order records | `acctnum`, `order_id` |
| `JanSales` | January 2019 sales transactions | `orderID`, `Product`, `Quantity`, `Price`, `orderdate`, `location` |
| `FebSales` | February 2019 sales transactions | `orderID`, `Product`, `Quantity`, `Price`, `orderdate`, `location` |

## Tools and SQL Skills

- MySQL
- Data validation and filtering
- Aggregate functions: `SUM`, `COUNT`, `AVG`, `MIN`, and `ROUND`
- `DISTINCT`, `GROUP BY`, `HAVING`, `ORDER BY`, and `LIMIT`
- `INNER JOIN` and `LEFT JOIN`
- Date and time filtering
- String matching with `LIKE`
- Revenue and customer-metric calculations

## Data Cleaning

Some source files contain repeated header rows inside the data. Valid orders are identified by keeping six-character order IDs and excluding the value `Order ID`.

```sql
WHERE CHAR_LENGTH(TRIM(orderID)) = 6
  AND TRIM(orderID) <> 'Order ID'
```

Using `TRIM()` also prevents extra spaces from causing valid records to be excluded.

## Business Questions

### Data Quality and Customer Analysis

1. Which customer records contain valid six-character order IDs?
2. How many distinct orders were placed in January?
3. How many distinct January orders included an iPhone?
4. Which customer accounts made purchases in February?
5. How many customers purchased more than two units in a transaction?
6. What were the average transaction value and average quantity in February?

### Product and Revenue Analysis

7. Which product had the lowest price?
8. What was the total January revenue?
9. How much revenue did each product generate in January?
10. Which product generated the highest January revenue?
11. Which battery products were sold in February?
12. Which products had prices ending in `.99`?
13. How many units of each headphone product were sold?

### Location and Time Analysis

14. Which orders were recorded between February 13 and February 18?
15. Where was the order placed on February 18 at 1:35 a.m.?
16. How many units were sold on February 18?
17. How many units of each product were sold in Los Angeles?
18. Which New York product-and-location combinations received more than two orders?
19. What products, units, and revenue were recorded at the selected Seattle address?

## Example Analysis

### Count Valid January Orders

```sql
SELECT COUNT(DISTINCT orderID) AS total_orders
FROM BIT_DB.JanSales
WHERE CHAR_LENGTH(TRIM(orderID)) = 6
  AND TRIM(orderID) <> 'Order ID';
```

### Calculate Total January Revenue

```sql
SELECT ROUND(SUM(Quantity * Price), 2) AS total_revenue
FROM BIT_DB.JanSales
WHERE CHAR_LENGTH(TRIM(orderID)) = 6
  AND TRIM(orderID) <> 'Order ID';
```

### Compare Revenue by Product

```sql
SELECT
    Product,
    SUM(Quantity) AS total_units,
    ROUND(SUM(Quantity * Price), 2) AS total_revenue
FROM BIT_DB.JanSales
WHERE CHAR_LENGTH(TRIM(orderID)) = 6
  AND TRIM(orderID) <> 'Order ID'
GROUP BY Product
ORDER BY total_revenue DESC;
```

### Identify the Lowest-Priced Product

```sql
SELECT
    Product,
    MIN(Price) AS minimum_price
FROM BIT_DB.JanSales
WHERE CHAR_LENGTH(TRIM(orderID)) = 6
  AND TRIM(orderID) <> 'Order ID'
GROUP BY Product
ORDER BY minimum_price
LIMIT 1;
```

### Connect February Purchases with Customer Accounts

```sql
SELECT DISTINCT c.acctnum
FROM BIT_DB.customers AS c
INNER JOIN BIT_DB.FebSales AS f
    ON c.order_id = f.orderID
WHERE CHAR_LENGTH(TRIM(f.orderID)) = 6
  AND TRIM(f.orderID) <> 'Order ID';
```

### Analyze Customers Purchasing More Than Two Units

```sql
SELECT
    COUNT(DISTINCT c.acctnum) AS total_customers,
    ROUND(AVG(f.Quantity * f.Price), 2) AS average_transaction_value
FROM BIT_DB.FebSales AS f
INNER JOIN BIT_DB.customers AS c
    ON f.orderID = c.order_id
WHERE f.Quantity > 2
  AND CHAR_LENGTH(TRIM(f.orderID)) = 6
  AND TRIM(f.orderID) <> 'Order ID';
```

### Analyze Los Angeles Product Demand

```sql
SELECT
    Product,
    SUM(Quantity) AS total_units
FROM BIT_DB.FebSales
WHERE location LIKE '%Los Angeles%'
  AND CHAR_LENGTH(TRIM(orderID)) = 6
  AND TRIM(orderID) <> 'Order ID'
GROUP BY Product
ORDER BY total_units DESC;
```

### Find New York Products with More Than Two Orders

```sql
SELECT
    location,
    Product,
    COUNT(DISTINCT orderID) AS total_orders_received
FROM BIT_DB.JanSales
WHERE CHAR_LENGTH(TRIM(orderID)) = 6
  AND TRIM(orderID) <> 'Order ID'
  AND location LIKE '%New York%'
GROUP BY location, Product
HAVING COUNT(DISTINCT orderID) > 2
ORDER BY total_orders_received DESC;
```

### Filter February Orders by Date Range

If `orderdate` is stored as text in `MM/DD/YY HH:MM` format, it should be converted before filtering:

```sql
SELECT orderdate
FROM BIT_DB.FebSales
WHERE STR_TO_DATE(orderdate, '%m/%d/%y %H:%i')
      BETWEEN '2019-02-13 00:00:00' AND '2019-02-18 23:59:59';
```

## Analytical Value

This analysis creates a foundation for understanding:

- Which products contribute the most revenue and unit sales.
- How product demand differs by city and store location.
- When sales activity occurs and which dates require closer review.
- How customer accounts connect with sales behavior.
- Where product, inventory, and marketing decisions can be supported by transaction data.

## Recommended Next Steps

- Combine the January and February tables using `UNION ALL` for month-over-month analysis.
- Extract city and state from the location field for cleaner geographic comparisons.
- Calculate average order value at the complete-order level rather than the individual line-item level.
- Analyze frequently purchased product combinations for cross-selling opportunities.
- Build a Tableau or Power BI dashboard showing revenue, units sold, top products, locations, and monthly trends.

## Conclusion

The project demonstrates how SQL can be used to clean transactional data, join customer and sales tables, calculate business metrics, and answer practical questions about customers, products, revenue, locations, and sales activity.
