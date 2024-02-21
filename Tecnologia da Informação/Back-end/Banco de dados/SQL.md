# SQL Examples

## SELECT

### BASIC Pattern

```sql
SELECT column1, column2, column3
FROM table_name
WHERE condition;
```

### Example

```sql
SELECT *
FROM customers
WHERE age >= 18;
```

### JOIN

#### INNER Example

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
INNER JOIN customers
ON orders.customer_id = customers.customer_id;
```

#### OUTER

##### LEFT Example

```sql
SELECT customers.customer_name, orders.order_id
FROM customers
LEFT OUTER JOIN orders
ON customers.customer_id = orders.customer_id;
```

##### RIGHT Example

```sql
SELECT customers.customer_name, orders.order_id
FROM customers
RIGHT OUTER JOIN orders
ON customers.customer_id = orders.customer_id;
```

##### RIGHT Pattern

```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```

##### RIGHT Example

```sql
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees
ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;
```

##### LEFT Example

```sql
SELECT customers.customer_name, orders.order_id
FROM customers
LEFT JOIN orders
ON customers.customer_id = orders.customer_id;
```

## CREATE

### TABLE

Example 1

```sql
CREATE TABLE customers (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  email VARCHAR(100),
  phone VARCHAR(20)
);
```

Example 2

```sql
CREATE TABLE COMPUTADORES (
  idComputador int PK,
  Sala varchar(30) NOT NULL,
  Responsavel varchar(255),
  Status varchar(10)
);
```

## ALTER

### TABLE Pattern

```sql
ALTER TABLE table_name
ADD column_name data_type [constraint],
MODIFY column_name data_type [constraint],
DROP column_name,
ADD CONSTRAINT constraint_name constraint_definition,
DROP CONSTRAINT constraint_name;
```

### INDEX Pattern

```sql
ALTER INDEX index_name
ADD column_name,
DROP column_name;
```

### VIEW Pattern

```sql
ALTER VIEW view_name
AS select_statement;
```

### PROCEDURE Pattern

```sql
ALTER PROCEDURE procedure_name
COMMENT 'Insert comment here';
```

## DROP

### TABLE Pattern

```sql
DROP TABLE table_name;
```

### INDEX Pattern

```sql
DROP INDEX index_name ON table_name;
```

### VIEW Pattern

```sql
DROP VIEW view_name;
```

### PROCEDURE Pattern

```sql
DROP PROCEDURE procedure_name;
```

## INSERT INTO

### Example

```sql
INSERT INTO students (id, name, major, gpa)
VALUES (1234, 'John Doe', 'Computer Science', 3.5);
```

## UPDATE

### Example 1

```sql
UPDATE students
SET major = 'Mathematics', gpa = 3.7
WHERE id = 1234;
```

### Example 2

Aumentar o preço dos produtos em estoque em 10%

```sql
UPDATE ESTOQUE SET PRECO = PRECO * 1.1;
```

## DELETE

### Example

```sql
DELETE FROM students
WHERE id = 1234;
```

## COMMANDS

### WHERE Example

```sql
SELECT name, department, salary
FROM employees
WHERE department = 'Sales' AND salary > 50000;
```

### GROUP BY Example

```sql
SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department;
```

### HAVING Example

```sql
SELECT customer_id, SUM(quantity) AS total_quantity
FROM orders
GROUP BY customer_id
HAVING SUM(quantity) >= 50;
```

### UNION Example

```sql
SELECT name, city
FROM customers
WHERE city = 'New York'
UNION
SELECT name, city
FROM employees
WHERE city = 'New York';
```

### CASE Pattern

```sql
CASE
  WHEN condition1 THEN result1
  WHEN condition2 THEN result2
  WHEN conditionN THEN resultN
  ELSE result
END;
```

### CASE Example

```sql
SELECT OrderID, Quantity,
CASE
  WHEN Quantity > 30 THEN 'The quantity is greater than 30'
  WHEN Quantity = 30 THEN 'The quantity is 30'
  ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;
```

## FUNCTIONS

### ROW_NUMBER() Pattern

```sql
SELECT column1, column2, ..., ROW_NUMBER() OVER (ORDER BY column1) AS row_num
FROM table_name;
```

### SUM() Pattern

```sql
SELECT column1, column2, ..., SUM(column3) OVER (PARTITION BY column1) AS column3_sum
FROM table_name;
```

### RANK() Pattern

```sql
SELECT column1, column2, ..., RANK() OVER (PARTITION BY column1 ORDER BY column3 DESC) AS rank_num
FROM table_name;
```

### AVG() Pattern

```sql
SELECT column1, column2, ..., AVG(column3) OVER (PARTITION BY column1) AS column3_avg
FROM table_name;
```
