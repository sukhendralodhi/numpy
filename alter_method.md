# ALTER

## USE CASES OF ALTER:

- Add new columns
- Remove columns
- Rename columns
- Change datatypes
- Set or Remove default values
- Add or Remove constraints
- Rename table

1. Add a new column ( - ALTER TABLE students)

 Syntax: ALTER TABLE students
         ADD COLUMN email VARCHAR(100); 

- All the rows will have the null values now be aware of that. for that you can have default value see the demonstration.  

Example: ALTER TABLE students
        ADD COLUMN email VARCHAR(100) DEFAULT 'Not Provided';

2. Delete a column from existing table

Syntax: ALTER TABLE students
        DROP COLUMN email;

- This will delete a column from your table

3. Rename column

Query: ALTER TABLE students
        RENAME COLUMN name to fullName;

4. Change data Type of column

Syntax: ALTER TABLE students
        ALTER COLUMN age TYPE SMALLINT;

5. Set a default value

Syntax: ALTER TABLE students
        ALTER COLUMN age SET DEFAULT 18; 

6. Remove default value

Syntax: ALETR TABLE students
        ALTER COLUMN age DROP DEFAULT;

# ADD A CONSTRAINT

Syntax: ALTER TABLE students
        ALTER COLUMN CONSTRAINT age_check CHECK (AGE >= 0);

- Note: If you didn't name the constraints manually while creating it, you'll need to find its auto generated name via pg-admin or pg_constraints;

# RENAME TABLE NAME

Syntax: ALTER TABLE students
        RENAME TO school_students;