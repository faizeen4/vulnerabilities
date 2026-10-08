# What is SQL injection (SQLi)?
###  SQL injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. This can allow an attacker to view data that they are not normally able to retrieve. This might include data that belongs to other users, or any other data that the application can access. In many cases, an attacker can modify or delete this data, causing persistent changes to the application's content or behavior. 

# SQL injection in different parts of the query

### Most SQL injection vulnerabilities occur within the WHERE clause of a SELECT query. Most experienced testers are familiar with this type of SQL injection.    However, SQL injection vulnerabilities can occur at any location within the query, and within different query types. Some other common locations where SQL injection arises are:

    In UPDATE statements, within the updated values or the WHERE clause.
    In INSERT statements, within the inserted values.
    In SELECT statements, within the table or column name.
    In SELECT statements, within the ORDER BY clause.

# SQL injection examples

## Retrieving hidden data

 Imagine a shopping application that displays products in different categories. When the user clicks on the Gifts category, their browser requests the URL:
https://insecure-website.com/products?category=Gifts

This causes the application to make a SQL query to retrieve details of the relevant products from the database:
SELECT * FROM products WHERE category = 'Gifts' AND released = 1

 The application doesn't implement any defenses against SQL injection attacks. This means an attacker can construct the following attack, for example:
https://insecure-website.com/products?category=Gifts'--

This results in the SQL query:
SELECT * FROM products WHERE category = 'Gifts'--' AND released = 1

Crucially, note that -- is a comment indicator in SQL. This means that the rest of the query is interpreted as a comment, effectively removing it. In this example, this means the query no longer includes AND released = 1. As a result, all products are displayed, including those that are not yet released. 

https://insecure-website.com/products?category=Gifts'+OR+1=1--

This results in the SQL query:
SELECT * FROM products WHERE category = 'Gifts' OR 1=1--' AND released = 1

The modified query returns all items where either the category is Gifts, or 1 is equal to 1. As 1=1 is always true, the query returns all items. 
