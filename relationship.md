# Relationship

- In a relationship database data is stored across multiple tables, and these tables are connected through relationships.

-  Instead of repeating the same data again and again in one huge table, we split into smaller, meaningful tables and connect them using key (primary and foreign keys).

## Relationships Type

1. One-To-One (1:1)
2. One-To-Many (1:N) (Most common)
3. Many-To-Many

## One To One Relationship

``` sql

students table
1. student_id (primary key)
2. name

```

``` sql

students profile table
1. student_id (foreign key)
2. address
3. phone_number

```

## Example:
- You have a students table -> each student has a unique student_id (primary key).
- You have student_profiles table -> each profile also has a unique student_id (foreign_key + Unique).

## One to Many Relationship

- You have a students table -> each student has a unique student_id (primary key).
- You also have students_marks table -> each row store marks for one subject, and contains a student_id as a foreign key.
- The same student_id can appear multiple times in student_marks, representing that one student has marks in multiple subjects.
- So, one student in the students table is connected to many rows in the student_marks table.  

## Many to Many Relationship

- In many-to-many, both tables (e.g. students, and courses) have multiple entries - and multiple relationship between them.
- So how can we talk about primary key -> foreign key relationships here?
- Doesn't primary key mean one unique row and many-to-many means multiple connections?
----
- In a many-to-many relationship, you don't directly connect the two tables using a foreign key.
- instead, you create a third table (called a junction table) that breaks the many-to-many into to one-to-many relationships.
---
## One To One Example

Now both the table have been created and we can clearly see there is a similar column and that is student_id but currently there is no relationship setup between them for setting them uo you have to create a foreign key in the 2nd table.

- primary key -> Unique indentify each row in a table.
- foriegn key -> Links one table to another by refrence to the Primary Key of that table.

``` sql
CREATE TABLE students (
	student_id SERIAL PRIMARY KEY,
	name VARCHAR(100) NOT NULL
);
```

``` sql
INSERT INTO students (name)
VALUES ('Sukhendra Lodhi'),
('Mohan Gupta'),
('Komal Sharma'),
('Arpita Patidar'),
('Sardar Banshkar');
```

```sql
CREATE TABLE student_profiles (
	student_id INT PRIMARY KEY,
	address TEXT,
	age INT,
	phone VARCHAR(15)
);
```

```sql
INSERT INTO student_profiles (student_id, address, age, phone)
VALUES
(1, 'Indore, India', 27, '9522543648'),
(2, 'Jabalpur, India', 22, '7800657456'),
(3, 'Gwalior, India', 24, '8755678954'),
(4, 'Dewas, India', 25, '6577564567'),
(5, 'Shivpuri India', 29, '7694963212');
```

```sql
ALTER TABLE student_profiles
ADD CONSTRAINT fk_student_id
FOREIGN KEY (student_id)
REFERENCES students(student_id);
```

# JOINS

- Joins are used to combine rows from two or more tables based on related columns, usually a primary key in one table and a foreign key in another.

#### "Think of JOINs as bridge between two tables that lets you query them together"

### Why do we use joins?

1. To merge related data spread across multiple tables.
2. To write meaningful real-world queries like: 
    - Which student scored highest in science?
    - List all students even if they haven't appeared for any exam.

## Join Type Description

1. INNER JOIN - Return only matching rows in both table

2. LEFT JOIN - Returns all rows from the left table, even if there's is no match in the right table

3. RIGHT JOIN - Retruns all rows from the right table, even if there's is no match in the left table

4. FULL JOIN - Return all rows from both table, fills null for missing match

5. CROSS JOIN - Returns cartesian product (every combination)