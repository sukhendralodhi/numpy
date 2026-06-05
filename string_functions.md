# String functions in PostgreSQL are used to manipulate text data like names, categories, sku_codes etc. 

1. They help you:
- Clean text
- Extract parts of a string
- Convert cases
- Replave or Remove Characters
- And much more

Let's see function one by one...

## First set of functions are Upper, Lower and length function.

1. make name in upper case

SELECT UPPER(name) FROM products;

2. make sku_code in lower case

SELECT LOWER(sku_code) FROM products;

3. get length of sku_code

SELECT LENGTH(sku_code) FROM products;

# Now let's see substring - it is used to extract some portion from your string.

- substring(text, location, length)

see the demonstration.

SELECT name, SUBSTRING(sku_code, 1,2) FROM products;


# NEXT SET OF FUNCTIONS ARE

LEFT() AND RIGHT() both have the use case similar to substring 
Get n leftmost and rightmost elements.

# CONCAT() AND CONCAT_WS() FUNCTIONS

- CONCAT() - provide a functionality so using that function you can concat two or more columns using that CONCAT() function you can just pass column name inside that function CONCAT(name, category, sku_code) this will concat the column but here for space you need to add ' ' with comma seprated 

SELECT CONCAT(name, ' ', category, ' ', sku_code) AS product_with_category FROM products;

- CONCAT_WS() - here no need to pass ' ' for space that will automatically give space you just mention in fisrt time what do you want between column during concatination

SELECT CONCAT_WS(' ', name, category, sku_code) AS product_with_category FROM products;