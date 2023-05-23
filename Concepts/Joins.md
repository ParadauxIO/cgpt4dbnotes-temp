There are different types of SQL joins in this I will discuss different examples using SQL syntax and tables. In SQL, a join is used to combine rows from two or more tables based on a related column between them. It enables users to select data from multiple tables as if the data were in one table.

For our examples, let's use two tables named ```Employees``` and ```Departments```. The ```Employees``` table has three fields: ```EmployeeID```, ```EmployeeName```, and ```DepartmentID```. The ```Departments``` table has two fields: ```DepartmentID``` and ```DepartmentName```.sql
```sql
CREATE TABLE Employees (
    EmployeeID int,
    EmployeeName varchar(255),
    DepartmentID int
);

CREATE TABLE Departments (
    DepartmentID int,
    DepartmentName varchar(255)
);
```

Here are four types of joins in SQL:INNER JOIN: The ```INNER JOIN``` keyword selects records that have matching values in both tables.sql
```sql
SELECT Employees.EmployeeName, Departments.DepartmentName 
FROM Employees 
INNER JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
```

In this example, ```INNER JOIN``` will return all rows from both tables where there is a match based on the condition ```Employees.DepartmentID = Departments.DepartmentID```.LEFT (OUTER) JOIN: The ```LEFT JOIN``` keyword returns all records from the left table (```Employees```), and the matched records from the right table (```Departments```). The result is NULL on the right side, if there is no match.sql
```sql
SELECT Employees.EmployeeName, Departments.DepartmentName 
FROM Employees 
LEFT JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
```

This query will return all the employees and their department names, if they are assigned to any. If an employee is not assigned to any department, the ```DepartmentName``` for that employee will be NULL.RIGHT (OUTER) JOIN: The ```RIGHT JOIN``` keyword returns all records from the right table (```Departments```), and the matched records from the left table (```Employees```). The result is NULL on the left side, if there is no match.sql
```sql
SELECT Employees.EmployeeName, Departments.DepartmentName 
FROM Employees 
RIGHT JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
```

This query will return all the departments and their associated employees. If there are any departments that have no employees assigned, they will still appear in the result set, but the ```EmployeeName``` for those departments will be NULL.FULL (OUTER) JOIN: The ```FULL OUTER JOIN``` keyword returns all records when there is a match in either the left (```Employees```) or the right (```Departments```) table records.sql
```sql
SELECT Employees.EmployeeName, Departments.DepartmentName 
FROM Employees 
FULL OUTER JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
```

This query will return all employees and their departments, if they are assigned to any, and all departments and their associated employees. If an employee is not assigned to any department, or if a department has no employees assigned, they will still appear in the result set, but the corresponding ```DepartmentName``` or ```EmployeeName``` will be NULL.SELF JOIN: A self join is a regular join, but the table is joined with itself.sql
```sql
SELECT E1.EmployeeName, E2.EmployeeName 
FROM Employees E1, Employees E2 
WHERE E1.EmployeeID != E2.EmployeeID 
AND E1.DepartmentID = E2.DepartmentID;
```

This query will return all pairs of employees who work in the same department.

Remember, all these examples are standard SQL, so they should work in any relational database management system, including Oracle, Microsoft SQL Server, MySQL, and PostgreSQL, among others. However, some systems might have their own additional types of joins or other specific syntax.

## JOIN...USING

The JOIN...USING clause is used to combine rows from two or more tables based on a specified column that has the same name in each table. It is a shorthand syntax for joining tables based on columns with matching names. Here's an example:

```sql
SELECT * FROM table1 JOIN table2 USING (column_name);
```