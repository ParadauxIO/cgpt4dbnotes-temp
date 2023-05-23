 Creating a table in SQL involves using the "CREATE TABLE" statement, where you specify the name of the table, and define its columns and their data types. Each column in a table is designed to hold a certain type of data, whether it's an integer, a string of text, dates, etc.

The general syntax is:sql
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);
```

Let's dissect the syntax:

CREATE TABLE: These are SQL keywords. The CREATE TABLE statement is used to create a new table in a database.

table_name: This is the name of the table that you want to create. Table names should be unique within the database.

column1, column2, ...: These are the names of the columns in the table. Like table names, column names should be unique within the table.

datatype: Each column in a table has a data type. The data type specifies what type of data the column can hold. SQL supports various data types like INT, VARCHAR, DATE, BOOLEAN, etc.

(...): Parentheses are used to list the column names and their data types.

Let's look at an example:sql
```sql
CREATE TABLE Employees (
    ID INT,
    Name VARCHAR(100),
    BirthDate DATE,
    IsFullTime BOOLEAN
);
```

In this case, we're creating a table called "Employees". This table has four columns:"ID": This column stores integers."Name": This column stores strings of characters, with a maximum length of 100."BirthDate": This column stores dates."IsFullTime": This column stores boolean values (i.e., TRUE or FALSE).

In some cases, you might also want to add constraints when creating tables. Constraints are used to limit the type of data that can be stored in a table. They can be column-level or table-level.

For example, you can specify a primary key for a table using the PRIMARY KEY constraint. A primary key uniquely identifies each record in a table. Let's modify the previous example:sql
```sql
CREATE TABLE Employees (
    ID INT PRIMARY KEY,
    Name VARCHAR(100),
    BirthDate DATE,
    IsFullTime BOOLEAN
);
```

In this case, "ID" is the primary key. No two records in this table can have the same "ID".

You can also set a default value for a column using the DEFAULT constraint, and the NOT NULL constraint to ensure that a column must always have a value. Here's an example:sql
```sql
CREATE TABLE Employees (
    ID INT PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    BirthDate DATE,
    IsFullTime BOOLEAN DEFAULT TRUE
);
```

In this example, every employee is considered full-time by default (unless specified otherwise), and every employee must have a name.

