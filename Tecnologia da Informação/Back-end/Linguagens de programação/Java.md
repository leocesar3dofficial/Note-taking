# Java

## JDBC

### Retrieve data from SQL query

```java
ResultSet rs = st.executeQuery(S);
```

1. **ResultSet**: `ResultSet` is an interface in Java that represents a table of data resulting from executing a SQL query. It's used to iterate over the results of a SELECT query.

2. **rs**: This is a variable of type `ResultSet`. It's used to store the results returned by the execution of the SQL query.

3. **st**: `st` seems to be an instance of `Statement` or its subclass, which is used to execute SQL queries against the database. This object is used to call the `executeQuery()` method.

4. **executeQuery(S)**: This method executes the SQL query represented by the string `S`. `S` is presumably a SQL SELECT statement. The `executeQuery()` method returns a `ResultSet` object containing the results of the query.

So, when you execute this line of code, it performs the SQL query represented by the string `S` using the statement object `st`, and the results are stored in the `ResultSet` object `rs`, which you can then iterate over to access the individual rows and columns returned by the query.
