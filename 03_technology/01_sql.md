# Create Table
### Code
```
CREATE TABLE [schema.]table (
{ column datatype [DEFAULT expr] [column_constraint]  }
[, { column datatype [DEFAULT expr] [column_constraint]  } ] );
```

### Example
```
CREATE TABLE employees_information
( id INT,
name VARCHAR(100) NOT NULL,
salary FLOAT DEFAULT 3000,
join_date DATE NOT NULL,
PRIMARY KEY (id) );
```

# Delete Table
### Code
```
DROP TABLE table_name;
```

### Example
```
DROP TABLE employees_information;
```

# Alter Table
### Code
```
ALTER TABLE table_name RENAME TO new_table name;
```

### Examples
#### Change table name
```
ALTER TABLE table_name RENAME COLUMN column_name TO column_new_name;
```

#### Change column name
```
ALTER TABLE table_name ADD column_name datatype [DEFAULT expr] [table_constraint];
```

#### Add a column
```
ALTER TABLE table_name ADD column_name datatype [DEFAULT expr] [table_constraint];
```

#### Delete a column
```
ALTER TABLE table_name DROP COLUMN column_name;
```

#### Change column type
```
ALTER TABLE table_name ALTER COLUMN column_name TYPE datatype;
```

#### Change column constraint
```
ALTER TABLE table_name ALTER COLUMN column_name SET constraint;
```

#### Delete a column constraint
```
ALTER TABLE table_name ALTER COLUMN column_name DROP constraint;
```

# Insert Rows
### Code
```
INSERT INTO table_name (column_1, column_2, column_3, …, column_n)
VALUES ('value_1', 'value_2', 'value_3', …, 'value_n');
```

### Example
```
INSERT INTO employees_information (id, name, salary, join_date)
VALUES ('1', 'Ahmed Ali Mahmoud', '35000', '2017-01-24');
```

# Insert Multiple Rows
### Code
```
INSERT INTO table_name (column_1, column_2, column_3)
VALUES ('value_1', 'value_2', 'value_3'),
('value_1', 'value_2', 'value_3'),
… ,
('value_1', 'value_2', 'value_3');
```

### Example
```
INSERT INTO employees_information (id, name, salary, join_date)
VALUES ('2', 'Nadir Ibrahim Fahad', '20000', '2017-10-12'),
('3', 'Iyad Sabir Hakeem', '10000', '2019-07-08'),
('4', 'Basma Omar Dawood', '15000', '2018-12-05'),
('8', 'Shefaa Turki Mohannad', '9000', '2019-06-27');
```

# Query / Find Row
### Code
```
SELECT [expressions] [table.column]
FROM table_name
[WHERE conditions]
[GROUP BY expression]
[ORDER BY expression]
[LIMIT expression];
```

# INNER JOIN
### Code
```
SELECT table1.column1, table1.column2, table1.column3, table2.column1, table2.column2
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```
### Example
```
SELECT id, emp_id, name, dept_id, dept_name
FROM employees_information
INNER JOIN employees_departments
ON id = emp_id;
```

# FULL OUTER JOIN
### Code
```
SELECT table1.column1, table1.column2, table1.column3, table2.column1, table2.column2
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```
### Example
```
SELECT id, emp_id, name, dept_id, dept_name
FROM employees_information
FULL OUTER JOIN employees_departments
ON id = emp_id;
```

# LEFT OUTER JOIN
### Code
```
SELECT table1.column1, table1.column2, table1.column3, table2.column1, table2.column2
FROM table1
LEFT OUTER JOIN table2
ON table1.column = table2.column;
```
### Example
```
SELECT id, emp_id, name, dept_id, dept_name
FROM employees_information
LEFT OUTER JOIN employees_departments
ON id = emp_id;
```

# RIGHT OUTER JOIN
### Code
```
SELECT table1.column1, table1.column2, table1.column3, table2.column1, table2.column2
FROM table1
RIGHT OUTER JOIN table2
ON table1.column = table2.column;
```
### Example
```
SELECT id, emp_id, name, dept_id, dept_name
FROM employees_information
RIGHT OUTER JOIN employees_departments
ON id = emp_id;
```

# CROSS JOIN
### Code
```
SELECT table1.column1, table1.column2, table1.column3, table2.column1, table2.column2
FROM table1
CROSS JOIN table2;
```
### Example
```
SELECT id, emp_id, name, dept_id, dept_name
FROM employees_information
CROSS JOIN employees_departments;
```
