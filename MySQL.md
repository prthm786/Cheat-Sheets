# MySQL Commands 

Listing Databases
```mysql 
  $ SHOW DATABASES;
```

**Creating a Database**
```mysql
  $ CREATE DATABASE db_name
```

Using Database 
```mysql
  $ USE db_name;
```
<br>


**Creating a Table** 
```mysql
  $ CREATE TABLE <table_name> (
    column_name datatype,
    column_name datatype
    );
```
<br>


Displaying the structure of the Table 
```mysql
  $ DESC table_name;
```
<br>


Inserting Values into the Table
```mysql
  $ INSERT INTO table_name>
    VALUES (value1, value2, ...);
```
<br>


Creating an Example Table of students and inserting into the table 
```mysql
  $ CREATE TABLE student_table (
     roll_no int,
     name varchar(255),
     subject varchar(255),
     marks int        
    );

  $ INSERT INTO student_table VALUES (21, "Henry", "Maths", 86), (15, "Jeff", "English", 58), (29, "Brad", "Science", 56), (15, "Brie", "History", 90);
```
<br>


**student_table**

 | roll_no | name  | subject | marks |
 | ------- | ----  | ------- | ----- |
 |    21   | Henry |  Maths  |   86  |
 |    15   | Jeff  | English |   58  |
 |    29   | Brad  | Science |   56  |
 |    15   | Brie  | History |   90  |


Adding a Column to Table
```mysql
  $ ALTER TABLE <table_name> 
    ADD column_name datatype;
```
<br>


Adding column to our student_table 
```mysql
  $ ALTER TABLE student_table 
    ADD dob date;
```
<br>


Updating Records 
```mysql
  -- Updating all Records 
  $ UPDATE table_name
    SET column_name = column_values;

  -- Updating Particular Records
  $  UPDATE table_name
     SET column_name = column_values
     WHERE condition;
```
<br>


Deleting Records 
```mysql
  -- Deleting All Records 
  $ DELETE FROM table_name;

  -- Deleting Particular Records
  $  DELETE FROM table_name
     WHERE condition;
```
<br>


**Selecting Columns**
```mysql
  -- Selecting a Single column 
  $ SELECT column_name FROM table_name;

  -- Selecting all columns
  $ SELECT * FROM table_name;
```
<br>


Select name column from our student_table 
```mysql
  $ SELECT name from student_table;
```
<br>



Using WHERE Clause with SELECT Statement
```mysql
  $ SELECT column_names
    FROM <table_name> 
    WHERE condition;
```
<br>


Selecting all the columns that have name = "Henry"
```mysql
 $ SELECT * FROM student_table 
   WHERE name = "Henry";
```
<br>


Using AND, OR, NOT and LIKE Operators with WHERE Clause 
```mysql
  $ SELECT column_names
    FROM table_name
    WHERE condition1 AND condition2    
    AND ...;

  $ SELECT column_names
    FROM table_name
    WHERE condition1 OR condition2 
    OR ...;

  $ SELECT column_names
    FROM table_name
    WHERE NOT condition;

  $ SELECT column1, column2, ...
    FROM table_name
    WHERE column_name LIKE pattern;
```
<br>


Using IS NULL and IS NOT NULL
```mysql
  -- Using IS NULL
  $ SELECT column_names
   FROM table_name
   WHERE column_name IS NULL;

  -- Using IS NOT NULL
  $ SELECT column_names
    FROM table_name
    WHERE column_name IS NOT NULL;
```
<br>


ORDER BY Clause 
```mysql
  -- Ascending Order
  $ SELECT column_names
    FROM table_name
    ORDER BY column_name ASC;

  -- Descending Order 
  $ SELECT column_names
    FROM table_name
    ORDER BY column_name DESC;
```
<br>


LIMIT Clause 
```mysql
  $ SELECT column_names
    FROM table_name 
    WHERE condition
    LIMIT number;
```
<br>


GROUP BY Clause 
```mysql
  $ SELECT column_names
    FROM table_name
    WHERE condition
    GROUP BY column_names
    ORDER BY column_names;
```
<br>


Using COUNT(), MIN(), MAX(), AVG(), SUM() 
```mysql
  -- COUNT() function
  $ SELECT COUNT(column_name)
    FROM table_name
    WHERE condition;

  -- AVG() function
  $ SELECT AVG(column_name)
    FROM table_name
    WHERE condition;

  -- SUM() function 
  $ SELECT SUM(column_name)
    FROM table_name
    WHERE condition;

  -- MIN() function
  $ SELECT MIN(column_name)
    FROM table_name
    WHERE condition;

  -- MAX() function 
  $ SELECT MAX(column_name)
    FROM table_name
    WHERE condition;
```
<br>


Deleting a Column
```mysql
  $ ALTER TABLE table_name
    DROP COLUMN column_name;
```
<br>


Deleting a Table 
```mysql
  $ DROP TABLE table_name;
```
<br>


Deleting a Database
```mysql
  $ DROP DATABASE db_name;
```
<br>