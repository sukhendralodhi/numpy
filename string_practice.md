STRING FUNCTION PRACTICE

1. Convert names to uppercase.

SELECT first_name, UPPER(last_name) FROM employees;

2. Convert text to lowercase email

SELECT first_name, LOWER(email) FROM employees;

3. Combine first and last names.

# INITCAP = This will make first latter capital of every words

SELECT INITCAP(CONCAT_WS(' ', first_name, last_name)) FROM employees;

4. Length of first name 

SELECT LENGTH(first_name) AS total_characters FROM employees;

5. get three first character from name

SELECT SUBSTRING(first_name, 1, 3) AS short_name FROM employees;

6. Replace gmail with company domain.

SELECT email, REPLACE(email, 'gmail.com', 'rcssoft.com') 
AS company_email 
FROM employees;

# POSITION
7. Find position of '@' in email

SELECT email, POSITION('@' IN email) AS at_position FROM employees;

# LEFT()

8. Get first 4 characters.

SELECT first_name,
       LEFT(first_name, 4)
FROM employees;

# RIGHT()

9. Get last 3 characters.

SELECT first_name,
       RIGHT(first_name, 3)
FROM employees;

# INITCAP()

10. capitalize first latter of words
 

SELECT INITCAP(first_name || ' ' || last_name)
FROM employees;

# TRIM()

11. remove spaces

SELECT TRIM('   PostgreSQL   ');

# SPLIT_PART()

12. get user name from email

SELECT email, SPLIT_PART(email, '@', 1) FROM employees;

