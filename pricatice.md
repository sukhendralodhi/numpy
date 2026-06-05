
CREATE TABLE assets (
 id INT PRIMARY KEY,
 product_name VARCHAR(100),
 sku_code VARCHAR(20),
 category VARCHAR(50),
 price DECIMAL(10,2)
);


# Question 1
-- this will give all the products thats sku_code start with W
SELECT * FROM assets
WHERE sku_code LIKE 'W%';

# Question 2

-- find the products thats sku_code second character is B

SELECT * FROM assets
WHERE sku_code LIKE '_B%';

Explanation
1. _ = exactly one character
2. B = second character must be B
3. % = any remaining characters

# Question 3
Find all products except Electronics

SELECT * FROM assets
WHERE category <> 'Electronics';

we can also write like this 

SELECT * FROM assets
WHERE category != 'Electronics';

# Question 4

Find products whose SKU ends with 09

SELECT * FROM assets
WHERE sku_code LIKE '%09';

# Question 5

Find products whose category starts with H

SELECT * FROM assets
WHERE category LIKE 'H%';

# Question 6

Find products with price greater than 1000

SELECT * FROM assets
WHERE price > 1000;

# Question 7

Find the most expensive product

SELECT * FROM assets
WHERE price = (SELECT MAX(price) FROM assets);

- here we are using subquery for getting most expensive product

<!-- OR -->

SELECT * FROM assets ORDER BY price DESC LIMIT 1;

- this will give you product that have max amount bcz in desceding order we get larget number order by price so that will order by price and also we set limit 1 so that will retutn only one result


# Question 8

- Count products in Electronics category

SELECT COUNT(*) AS total_product_electronics FROM assets
WHERE category = 'Electronics';

# Question 9

Find average product price

SELECT ROUND(AVG(price), 2) AS avg_price FROM assets;

- this will give you average round of two decimal place

OR

SELECT AVG(price) AS avg_price FROM assets;

- this will give you average including all the decimal points 
