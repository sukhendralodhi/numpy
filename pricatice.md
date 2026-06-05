
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