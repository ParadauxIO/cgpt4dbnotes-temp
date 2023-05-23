
```SQL
CREATE TABLE Employees (
    ID INT PRIMARY KEY,
    Name VARCHAR(30),
    Age INT,
    Salary DECIMAL(10,2)
);
```READ (SELECT):SQL
```SQL
SELECT column1, column2, ...
FROM table_name;
```

```SQL
SELECT * FROM table_name;
```

```SQL
SELECT Name, Salary FROM Employees;
```

UPDATE
```SQL
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

```SQL
UPDATE Employees
SET Salary = 5000
WHERE ID = 1;
```

DELETE:SQL
```SQL
DELETE FROM table_name WHERE condition;
```

```SQL
DELETE FROM Employees WHERE ID = 1;
```

Please replace ```table_name```, ```column```, ```datatype```, ```value``` and ```condition``` with your actual table names, column names, datatypes, values and conditions. And be extremely careful with UPDATE and DELETE statements - without a WHERE clause, these statements will update or delete all rows in your table!

INSERT
```SQL
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

If you're inserting values into every column in the table in the order they exist, you don't need to specify the column names:SQL
```SQL
INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

Example:SQL
```SQL
INSERT INTO Employees (ID, Name, Age, Salary)
VALUES (1, 'John', 30, 5000.00);

-- or

INSERT INTO Employees
VALUES (2, 'Jane', 25, 6000.00);
```

In these examples, please replace ```table_name```, ```column```, ```value``` with your actual table names, column names, and values.

