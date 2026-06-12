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