# Now if you have the knowledge of language you might know about operators.
# Some of the basics operators are:
1. Comparison (=,>,<,!=,<=,>=)
2. Range(Between)
3. Set(IN)
4. Pattern (LIKE)
5. Logical (AND, OR, NOT)


## Comparison
<!-- 1. =, != -->
<!-- 
SELECT * FROM products WHERE category = 'Electronics';
SELECT * FROM products WHERE category != 'Electronics';
 -->

<!-- 2. > -->

<!-- 
SELECT * FROM products WHERE price > 1000;
 -->

<!-- 3. < -->

<!-- 
SELECT * FROM products WHERE stock_quantity < 30;
 -->

## Logical Operator

<!-- 
SELECT * FROM products WHERE price < 1000 AND category = 'Electronics';
 -->

 <!-- 
 SELECT * FROM products 
WHERE category = 'Electronics' 
OR category = 'Fitness' 
OR category = 'Accessories';
  -->

## Range (BETWEEN)

<!-- 
SELECT * FROM products WHERE price BETWEEN 400 AND 1000;
 -->

## IN 

<!-- 
SELECT * FROM products WHERE category IN('Electronics', 'Fitness', 'Accessories');
 -->

## PATTERN (LIKE)


<!-- This will give result that fisrt latter start with W -->

<!-- 
SELECT * FROM products 
WHERE sku_code LIKE 'W%';
 -->

<!-- this means leave the fisrt letter but second latter must be start with B then whatever text no issue -->

<!-- 
SELECT * FROM products
WHERE sku_code LIKE '_B%';
 -->