These are also known as conditional operators, and are used to test for truth or falsehood, typically when querying databases or filtering results.

The basic comparison operators in SQL are:

1.  **`=`**: Equality. For example, `SELECT * FROM Students WHERE Age = 18;` will select all students whose age is exactly 18.

2.  **`<>` or `!=`**: Inequality. Either can be used, though <> is more standard SQL. For example, `SELECT * FROM Students WHERE Age <> 18;` will select all students whose age is not 18.

3.  **`<`**: Less than. For example, `SELECT * FROM Students WHERE Age < 18;` will select all students younger than 18.

4.  **`>`**: Greater than. For example, `SELECT * FROM Students WHERE Age > 18;` will select all students older than 18.

5.  **`<=`**: Less than or equal to. For example, `SELECT * FROM Students WHERE Age <= 18;` will select all students 18 or younger.

6.  **`>=`**: Greater than or equal to. For example, `SELECT * FROM Students WHERE Age >= 18;` will select all students 18 or older.


Additionally, SQL has the `LIKE` and `IN` operators, and the `BETWEEN` condition:

7.  **`LIKE`**: Allows for simple pattern matching. You can use two wildcard operators with `LIKE`: "%" and "_". "%" represents zero, one, or multiple characters, and "_" represents a single character. So, `SELECT * FROM Students WHERE Name LIKE 'A%';` will select all students whose names start with "A".

8.  **`IN`**: Allows you to specify multiple values in a WHERE clause. For example, `SELECT * FROM Students WHERE Name IN ('Alice', 'Bob');` will select all students whose names are either Alice or Bob.

9.  **`BETWEEN`**: Allows you to select values within a given range. The values can be numbers, text, or dates. For example, `SELECT * FROM Students WHERE BirthDate BETWEEN '2001-01-01' AND '2003-12-31';` will select all students born in 2001, 2002, or 2003.


In SQL, `NULL` is a special marker used to indicate that a data value does not exist in the database. The `IS NULL` and `IS NOT NULL` operators allow for these checks:

10.  **`IS NULL`**: Tests for null values. For example, `SELECT * FROM Students WHERE MiddleName IS NULL;` will select all students who don't have a middle name.

11.  **`IS NOT NULL`**: Tests for non-null values. For example, `SELECT * FROM Students WHERE MiddleName IS NOT NULL;` will select all students who do have a middle name.

When it comes to dates, these comparison operators can be used as expected. However, when working with dates, it's crucial to format the dates correctly. SQL uses the 'YYYY-MM-DD' format by default. Using `LIKE` with dates doesn't make much sense, but `BETWEEN`, `=`, and the others can be very useful. For example, `SELECT * FROM Orders WHERE OrderDate >= '2023-01-01';` will select all orders placed in 2023 or later.

The operators work with time values as well. For example, `SELECT * FROM Meetings WHERE StartTime >= '08:00:00';` will select all meetings that start at or after 8 AM.

SQL also has logical operators: `AND`, `OR`, and `NOT`. These can be used to combine or invert conditions:

-   **`AND`**: All conditions must be true for the row to be included in the result set.
-   **`OR`**: If any condition is true, the row is included in the result set.
-   **`NOT`**: Inverts the result of the condition.

For example, `SELECT * FROM Students WHERE Age >= 18 AND Name LIKE 'A%';` will select all students aged 18 or older whose names start with "A".

Keep in mind that while this covers standard SQL, some databases have their own additional operators. Be sure to consult the documentation for the database you're using if you run into unfamiliar operators.