**User**: Show a practical example of DBMS set operations with corresponding sql

--------
In the context of DBMS (Database Management System), set operations are operations that can be performed on sets of data. The three fundamental set operations are UNION, INTERSECT, and MINUS (also known as EXCEPT in some DBMS). These operations allow you to manipulate and return sets of data from different tables. Let's consider two tables: 'Orders' and 'Customers' for a demonstration:

Orders tableOrderIDCustomerIDProduct1101Apple2102Banana3103Cherry4101Durian5104Eggfruit

Customers tableCustomerIDName101Alice102Bob103Charles105David106EmilyUNION: The UNION operation combines the result set of two or more SELECT statements (each SELECT statement within the UNION must have the same number of columns).

Example: Get all unique ```CustomerID```s from both ```Orders``` and ```Customers``` tables.sql
```sql
SELECT CustomerID FROM Orders
UNION
SELECT CustomerID FROM Customers;
```
INTERSECT: The INTERSECT operation returns the intersecting part of two SELECT statements (common results from both SELECT statements).

Example: Get ```CustomerID```s that are present in both ```Orders``` and ```Customers``` tables.sql
```sql
SELECT CustomerID FROM Orders
INTERSECT
SELECT CustomerID FROM Customers;
```
MINUS (EXCEPT): The MINUS operation returns the difference between the first and the second SELECT statements (returns elements of the first set not present in the second).

Example: Get ```CustomerID```s that are in ```Customers``` table but not in ```Orders``` table.sql
```sql
SELECT CustomerID FROM Customers
MINUS
SELECT CustomerID FROM Orders;
```

Note: Some databases (like MySQL) don't support MINUS or EXCEPT operators directly. You have to use other techniques (like a LEFT JOIN with a WHERE IS NULL clause) to achieve the same results.

Please make sure to replace ```MINUS``` with ```EXCEPT``` if you are using a DBMS like PostgreSQL or SQL Server.

Also, please ensure you have necessary permissions and the data used in the example should not violate privacy regulations.

