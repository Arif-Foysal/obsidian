#dbms #Computer-Science #uiu 

> [!Contents]
>- [[SQL Key Types]]
>- [[Problem Statement 01 classicmodels]]
>- [[Relational Databases]]
>- [[Database Model]]
>	- [[Entity Relationship Diagram (ERD)]]
>- [[Database Schema]]
>- [[SQL]]
>	- [[SQL Statements and Syntax]] 
>	- [[Listing Databases]]
>	-
>	- [[Comments in SQL]]
>- [[Database Normalization]]
>- [[DBMS Lab-04 Assignment]]


**What is a Database?**
A database is an organized collection of structured information, typically stored in the form of tables (rows/records & columns/fields). Relational databases allow storing and retrieving different kinds of related information e.g. products, customers, and orders for an online shopping site. Structured Query Language or SQL (pronounced "sequel") is the most widely used language for interacting with relational databases, and is an essential skill for Data Science professionals.

#### Viewing Data from a table
The `SELECT` statement is used to select data from a database.
The data returned is stored in a result table, called the result-set.
The simplest way to view data from the table is using the `SELECT` statement. It has the following syntax:
```sql
SELECT column1, column2, ... FROM table_name;
```
It will only show the data of the specifies columns.

You can show data from all columns using [[SQL WildCards]] -
```sql
SELECT * FROM `<tableName>`;
```
To return data from all of the column of our `offices` table-
```
SELECT * FROM `offices`;
```
**Output/Result Table-**
```
+------------+---------------+------------------+--------------------------+--------------+------------+-----------+------------+-----------+
| officeCode | city          | phone            | addressLine1             | addressLine2 | state      | country   | postalCode | territory |
+------------+---------------+------------------+--------------------------+--------------+------------+-----------+------------+-----------+
| 1          | San Francisco | +1 650 219 4782  | 100 Market Street        | Suite 300    | CA         | USA       | 94080      | NA        |
| 2          | Boston        | +1 215 837 0825  | 1550 Court Place         | Suite 102    | MA         | USA       | 02107      | NA        |
| 3          | NYC           | +1 212 555 3000  | 523 East 53rd Street     | apt. 5A      | NY         | USA       | 10022      | NA        |
| 4          | Paris         | +33 14 723 4404  | 43 Rue Jouffroy D'abbans | NULL         | NULL       | France    | 75017      | EMEA      |
| 5          | Tokyo         | +81 33 224 5000  | 4-1 Kioicho              | NULL         | Chiyoda-Ku | Japan     | 102-8578   | Japan     |
| 6          | Sydney        | +61 2 9264 2451  | 5-11 Wentworth Avenue    | Floor #2     | NULL       | Australia | NSW 2010   | APAC      |
| 7          | London        | +44 20 7877 2041 | 25 Old Broad Street      | Level 7      | NULL       | UK        | EC2N 1HN   | EMEA      |
+------------+---------------+------------------+--------------------------+--------------+------------+-----------+------------+-----------+
```
#### SQL SELECT DISTINCT Statement
The `SELECT DISTINCT` statement is used to return only distinct (different) values.

Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.
**SELECT DISTINCT Syntax-**
```sql
SELECT DISTINCT <column1>, <column2>, ...  
FROM `table_name`;
```
The following SQL statement lists the **number** of different (distinct) customer countries:
```sql
SELECT COUNT(DISTINCT <column1>) FROM Customers;
```

#### SQL WHERE Clause
The `WHERE` clause is used to filter records.

It is used to extract only those records that fulfill a specified condition.
##### Where Syntax
```sql
SELECT <column1>, <column2>, ...  
FROM <table_name>  
WHERE <condition>;
```
For Example:
```sql
SELECT * FROM `employees` WHERE `jobTitle`="Sales Rep";
```

The `WHERE` clause supports the following operators:

| Operator | Description                                      |     |
| -------- | ------------------------------------------------ | --- |
| =        | Equal                                            |     |
| >        | Greater than                                     |     |
| <        | Less than                                        |     |
| >=       | Greater than or equal                            |     |
| <=       | Less than or equal                               |     |
| <> or != | Not equal                                        |     |
| BETWEEN  | Between a certain range                          |     |
| LIKE     | Search for a pattern                             |     |
| IN       | To specify multiple possible values for a column |     |

Expressions within a `WHERE` clause can be combined using `AND` and `OR`.

```
SELECT <column1>, <column2>, ...
FROM <table_name>
WHERE <condition1> AND <condition2> AND <condition3> ...;
```

An expression within a `WHERE` clause can be negated using `NOT`.

```
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```



**References**
[Relation Databases-Jovian](https://jovian.com/aakashns/relational-databases-and-sql)
[W3Schools-SQL](https://www.w3schools.com/sql/)


