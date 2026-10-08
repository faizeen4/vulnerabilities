# What is SQL injection (SQLi)?
## SQL injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. This can allow an attacker to view data that they are not normally able to retrieve. This might include data that belongs to other users, or any other data that the application can access. In many cases, an attacker can modify or delete this data, causing persistent changes to the application's content or behavior. 

# SQL injection in different parts of the query

## Most SQL injection vulnerabilities occur within the WHERE clause of a SELECT query. Most experienced testers are familiar with this type of SQL injection.    However, SQL injection vulnerabilities can occur at any location within the query, and within different query types. Some other common locations where SQL injection arises are:

    In UPDATE statements, within the updated values or the WHERE clause.
    In INSERT statements, within the inserted values.
    In SELECT statements, within the table or column name.
    In SELECT statements, within the ORDER BY clause.
