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


## Recommended Next Steps

- Combine the January and February tables using `UNION ALL` for month-over-month analysis.
- Extract city and state from the location field for cleaner geographic comparisons.
- Calculate average order value at the complete-order level rather than the individual line-item level.
- Analyze frequently purchased product combinations for cross-selling opportunities.
- Build a Tableau or Power BI dashboard showing revenue, units sold, top products, locations, and monthly trends.

## Conclusion

The project demonstrates how SQL can be used to clean transactional data, join customer and sales tables, calculate business metrics, and answer practical questions about customers, products, revenue, locations, and sales activity.
