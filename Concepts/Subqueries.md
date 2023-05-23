SQL sub-queries, also known as subselects or nested queries, are queries embedded within the main SQL query. They can return data that will be used in the main query as a condition to further restrict the data to be retrieved. They are used when the data to be retrieved is affected by the data from another separate query.

Here is the general syntax of a subquery:sql
```sql
SELECT column_name [, column_name ]
FROM   table1 [, table2 ]
WHERE  column_name OPERATOR
   (SELECT column_name [, column_name ]
   FROM table1 [, table2 ]
   [WHERE])
```

Types of SQL Sub-Queries

There are two main types of subqueries:

Correlated Subqueries: These are subqueries that depend on the outer SQL query for their values. This means that the subquery is executed once for every row processed by the outer query. The correlated subquery can also reference values from the outer query.

Non-Correlated Subqueries: These are subqueries that can be run independently of the outer query. They run first, return their results, and their results are used by the main query.

Places to Use Sub-Queries

Subqueries can be used in various parts of a query, including:In the SELECT clauseIn the FROM clauseIn the WHERE clauseIn the HAVING clause

Examples of SQL Sub-Queries

Here are some examples to illustrate how sub-queries are used in SQL:

Example 1: Finding all customers who have made orders above the average order amount.sql
```sql
SELECT customer_name, customer_email 
FROM customers
WHERE customer_id IN (
    SELECT customer_id 
    FROM orders 
    WHERE order_amount &gt; (
        SELECT AVG(order_amount) 
        FROM orders
    )
)
```

In this example, the innermost subquery calculates the average order amount. The middle subquery then finds all orders with an amount greater than this average. The outer query then retrieves the details of customers who made these orders.

Example 2: Using sub-query in FROM clause.sql
```sql
SELECT AVG(order_amount) AS avg_order_amount
FROM (
    SELECT customer_id, SUM(order_amount) AS order_amount
    FROM orders
    GROUP BY customer_id
) AS customer_orders
```

In this example, the subquery aggregates orders per customer, and the main query calculates the average order amount across all customers.

Remember, the key to using subqueries effectively is understanding the data and the relationships between different tables, as well as what you want to extract from these tables.

Subquery Performance Considerations

One important consideration when using subqueries is performance. Since subqueries can be executed once for each row selected by the outer query, they can slow down performance. Therefore, it's essential to ensure that the subquery is as efficient as possible, for example, by ensuring that it's working on a set of data as small as possible.

Some DBMSs are more optimized for subqueries than others. Sometimes, you may achieve better performance by rewriting the query to use JOINs instead of subqueries. As always with SQL, ensure to test different approaches and choose the most efficient one for your specific case.

