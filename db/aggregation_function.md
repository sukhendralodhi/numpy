# Aggregation Functions
Aggregation function are used to summarize data.
Instead of looking ate every single row, we use these functions to get overall insights, like:

1. How many rows are there?
2. What's the total price?
3. What's the average stock?
4. What's the max/min value in column?

# COUNT 
1. Count number of rows (Total number of products)
<!-- 
SELECT COUNT(product_id) AS total_product FROM products;
 -->

# SUM
1. Add numeric values (Total stock in category)

<!-- 
SELECT SUM(price) AS all_product_total FROM products;
 -->

<!-- 
SELECT SUM(price) AS all_product_total FROM products WHERE category = 'Electronics';
 -->

<!-- 
SELECT SUM(price) AS all_product_total FROM products WHERE category = 'Electronics' OR category = 'Fitnes';
 -->

# AVG 
1. Calculate average (Average price of accessories)

<!-- 
SELECT ROUND(AVG(price),2) AS total_avg FROM products;
 -->

# MIN
1. Find smallest value (Cheapest product)

# MAX
1. Find highest value (Most expensive product)


<!-- Question: -->
<!-- Find the most expensive product in each category (name and price) -->

<!-- 
SELECT category, name, price 
FROM products p1
WHERE price = (
    SELECT MAX(price) 
    FROM products p2 
    WHERE p2.category = p1.category
);
 -->

 <!-- Question: -->

 <!-- Show all uniques categories in uppercase, sorted in descending order. -->

 