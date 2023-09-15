# MySQL Commands 

Listing Databases
```
  $ SHOW DATABASES;
```

Creating a Database
```
  $ CREATE DATABASE <db_name>
```

Using Database 
```
  $ USE <db_name>;
```

Creating a Table 
```
  $ CREATE TABLE <table_name> (
    <column_name> <datatype>,
    <column_name> <datatype>
    );
```

Displaying the structure of the Table 
```
  $ DESC <table_name>;
```

Inserting Values into the Table
```
  $ INSERT INTO <table_name> VALUES (<value1>, <value2>, ...);
```

Creating an Example Table of students and inserting into the table 
``` 
  $ CREATE TABLE student_table (
     roll_no int,
     name varchar(255),
     subject varchar(255),
     marks int        
    );

  $ INSERT INTO student_table VALUES (21, "Henry", "Maths", 86), (15, "Jeff", "English", 58), (29, "Brad", "Science", 56), (15, "Brie", "History", 90);
```

**student_table**

| roll_no | name  | subject | marks |
| ------- | ----  | ------- | ----- |
|    21   | Henry |  Maths  |   86  |
|    15   | Jeff  | English |   58  |
|    29   | Brad  | Science |   56  |
|    15   | Brie  | History |   90  |


Adding a Column to Table
```
  $ ALTER TABLE <table_name> ADD <column_name> <datatype>;
```

Adding column to our student_table 
```
  $ ALTER TABLE student_table ADD dob date;
```
```





Deleting a Column
```
  $ ALTER TABLE <table_name> DROP COLUMN <column_name>;
```

Deleting a Table 
```
  $ DROP TABLE <table_name>;
```

Deleting a Database
```
  $ DROP DATABASE <db_name>;
```
