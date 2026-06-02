# CLAUSE 
<!-- Defination  -->
Clauses are mainly used for quering a data and are kind of building blocks even you all using them from the start. 

1. SELECT => Choose which column to display
2. FROM => Specify the table
3. WHERE => Filter row based on conditions
4. GROUP BY => Group row for aggregations
5. HAVING => Filter aggregated groups (used after GROUP BY)
6. ORDER BY => Sort the result in ascending or descending order
7. LIMIT => Limit the numbers of row returned
8. AS => Rename columns or tables temporarily (aliasing)
9. DISTINCT => Return only unique/distinct values


# SELECT 
<!-- 1. SELECT name, price FROM products;? -->

# WHERE
<!-- 2. SELECT * FROM products 
WHERE category = 'Electronics'; -->

# GROUP BY (GROUP OF UNIQUE VALUES)
<!-- SELECT category FROM products GROUP BY category; -->

# HAVING
<!-- SELECT category, COUNT(*) FROM products  -->
<!-- GROUP BY category -->
<!-- HAVING COUNT(*) > 1; -->

<!-- 
CREATE TABLE sales (
    id SERIAL PRIMARY KEY,
    product_name VARCHAR(50),
    amount NUMERIC
);

INSERT INTO sales (product_name, amount)
VALUES
('Laptop', 50000),
('Laptop', 60000),
('Mouse', 500),
('Mouse', 700),
('Keyboard', 1500);

SELECT product_name,
       SUM(amount) AS total_sales
FROM sales
GROUP BY product_name
HAVING SUM(amount) > 10000;
 -->

# ORDER BY

<!--  
SELECT * FROM products ORDER BY price ASC;
SELECT * FROM products ORDER BY price DESC;
-->

# LIMIT

<!-- 
SELECT * FROM products LIMIT 3;
 -->

# AS

<!-- 
SELECT name AS item_name, price AS item_price FROM products;
 -->

# DISTINCT

<!-- 
SELECT DISTINCT category FROM products;
 -->