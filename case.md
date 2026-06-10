# CASE

 - CASE is condionla expression in SQL that works like an if-else or switch statement. It lets you return different value based on different constions all within a single query.

 # WHY DO WE USE CASE?

 - To create custom column on the fly
 - To categories data based on certain logic
 - To replace value conditionally
 - To handle null or missing values gracefully
 - To simplify complex logic inside SELECT queries 

 # Syntax of CASE in SQL

```sql
SELECT
    column1,
    CASE
        WHEN condition1 THEN result1
        WHEN condition2 THEN result2
        ...
        ELSE default_result
    END AS new_column_name
FROM table_name;
```

- Best way to learn the CASE is using a simple example where you will add a custom column in which you will have price_tag. 
- If the price is above 1000 you will say it is expensive.
- If the price is between 500 and 1000 you will say it is moderate.
- And if the price is below 500 it is cheap.

## Example 1

``` sql
ALTER TABLE products
ADD COLUMN price_tag TEXT;

UPDATE products
SET price_tag = 
CASE
	WHEN price >= 1000 THEN 'Expensive'
	WHEN price BETWEEN 500 AND 1000 THEN 'Moderate'
	ELSE 'Cheap'
END;
```

## Example 2

```sql
SELECT name, is_available,
CASE
	WHEN is_available = true THEN 'In Stock'
	ELSE 'Out Of Stock'
END AS stock_status
FROM products;
```

## Example 3

```sql
SELECT name, stock_quantity,
CASE
	WHEN stock_quantity >= 100 THEN 'Hight Stock'
	WHEN stock_quantity BETWEEN 30 AND 100 THEN 'Medium Stock'
	ELSE 'Low Stock'
END AS label
FROM products;
```