#dbms #Computer-Science #uiu 

> [!Contents]
>- [[SQL Key Types]]
>- [[Problem Statement 01 classicmodels]]
>- 
>- [[Comments in SQL]] 

**What is a Database?**
A database is an organized collection of structured information, typically stored in the form of tables (rows/records & columns/fields). Relational databases allow storing and retrieving different kinds of related information e.g. products, customers, and orders for an online shopping site. Structured Query Language or SQL (pronounced "sequel") is the most widely used language for interacting with relational databases, and is an essential skill for Data Science professionals.

## Relational Databases
There are many ways of storing data on a computer (text files, [[JSON]] files, [[CSV]] files, spreadsheets etc.). A relational database is a data storage system with the following properties:

1. Data is stored in tables e.g. `customers`, `products`, `offices`, `employees`, etc..
2. Each table has a set of columns. Each column is used to store a specific type of data.
3. Data is stored as rows (also called records) within database tables.
4. Tables support CRUD operations on rows: Create, Read, Update and Delete
5. Table can be connected to other tables using relationship constraints (e.g. an employee works at a specific office).
6. Information can be retrieved from the database using the Structured Query Language (SQL)
7. Databases can be hosted locally (on your computer) or on the cloud, for distributed access.

Here's what a table in a relational database looks like:
![[RD_Sample_Table.bmp]]

## Entity Relationship Diagram (ERD)
An Entity Relationship Diagram (ERD) describes all the table within the database and the relations between them. ERDs can be created using drawing tools like [LucidChart](https://jovian.com/outlink?url=https%3A%2F%2Fwww.lucidchart.com%2Fpages%2Fhow-to-draw-ERD). Here's the ERD for the Classic Models database:
![[ERD_Sample.bmp]]

## Relational Database Software
There are several relational database software packages. Some are free and open source, while others are paid and proprietary. Here some popular relational database distributions:
1. MySQL
2. Postgres
3. SQLite
4. Microsoft SQL Server
5. MariaDB
6. Oracle
7. IBM DB2
we'll use [MySQL](https://jovian.com/outlink?url=https%3A%2F%2Fwww.mysql.com%2F), a free and open source relational database.
## Structured Query Language

Structured Query Language or SQL is a programming language for interacting with relational databases. Unlike general purpose programming languages like Python, Java, C++ etc., SQL has a very limited syntax.
## SQL Statements and Syntax
There are three types of SQL statements:

**1. Data Definition Language(DDL):** The Data Definition Language contains commands that are less frequently used. DDL commands modify the actual structure of a database, rather than the database’s contents. example:

- Generating a table
- Modifying a structure of a table (altering)

**2. Data Control Language(DCL):** The Data Control Language allows you to manipulate and manage user access rights on database objects. It consists of two commands:

- the GRANT command, used to add database permissions for a user,
- and the REVOKE command, used to remove existing permissions.

These two commands form the core of the relational database security model.

**3. Data Manipulation Language (DML):** Data Manipulation Language contains the subset of SQL commands used most frequently. It is used for searching, inserting, updating, and deleting data that we will see in this notebook.

Some quick notes on the SQL syntax:

- SQL is case insensitive. You can type statements in upper case, lowercase or a mixture of both
- Database names can be typed with or without backquotes i.e. `classicmodels` or `` `classicmodels` ``
- SQL statement can span over multiple lines and must end with a semicolon `;`
- The statements in this tutorial can be executed on the MySQL command line or the workbench

The SQL syntax for each relational database software package is slightly different. Check the official documentation of your DB for details.

## Working with Databases
### Listing Databases
To display available databases, use the statement:
```
SHOW DATABASES;
```

Output:
```sql
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.01 sec)

```

### Creating Databases
Databases can be created using the `CREATE DATABASE` statement.
```sql
CREATE DATABASE `classicmodels`;
```

Once created, the database should appear in the list of databases
```
SHOW DATABASES;
```

Output:
```sql
+--------------------+
| Database           |
+--------------------+
| classicmodels      |
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)
```
We can also conditionally create a database if it doesn't already exist using:
```
CREATE DATABASE IF NOT EXISTS `classicmodels`;
```

### Selecting a Database
A database must be selected before it can be used. This is done with the `USE` statement.
```sql
USE `classicmodels`;
```
All future statements like listing tables, creating tables, inserting or querying data will use the selected database.
### Deleting Databases
To delete a database, use `DROP DATABASE`
```sql
DROP DATABASE `classicmodels`;
```
The database will no longer show up in the list of databases.
```sql
SHOW DATABASES;
```

Output:
```sql
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.01 sec)
```

Can you rename an existing database???
[[Renaming an Existing Database]]

### SQL Data Types
[[SQL Data Types]]

### Working With Tables
Let's create the tables for the Classic Models database according to the given Entity Relationship Diagram. We will also insert some data along the way.

- Tables in a database can be listed using the `SHOW TABLES` statement
- Tables are created using the `CREATE TABLE` statement
- Tables are deleted using the `DROP TABLE` statement
- You can view the structure of a table using the `DESCRIBE` statement
- Data can be inserted into a table using the `INSERT INTO` statement
#### Creating Tables
While creating tables, we specify a list of columns and the data type for each column.
You can create tables by the following syntax-
```sql
CREATE TABLE <table_name> (
    <column1> <datatype> <constraint>,
    <column2> <datatype> <constraint>,
    ...
);
```
>- **Note that a table must have at least 1 column**

Let's explain the components of the syntax:
- `CREATE TABLE table_name`: This specifies the name of the table you want to create.
- `( ... )`: Within the parentheses, you define the columns and their properties.
- `column1, column2, ...`: These represent the names of the columns you want to include in the table.
- `datatype`: The datatype specifies the type of data that can be stored in each column. For example, you can use `INT` for integers, `VARCHAR(n)` for variable-length strings of maximum length `n`, `DATE` for dates, etc. Choose the appropriate datatype for each column based on the type of data you want to store.
- `constraint`: Constraints are optional and define rules or conditions that the data in a column must follow. Common constraints include `PRIMARY KEY` (ensures uniqueness and serves as the primary identifier for a row), `NOT NULL` (requires a column to have a value and not be empty), `UNIQUE` (ensures uniqueness across rows), `FOREIGN KEY` (establishes a relationship between two tables), and more.

Now with that said, let's create offices table for our [[Problem Statement 01 classicmodels]]

```sql
CREATE TABLE `offices` (              
	  `officeCode` varchar(10) NOT NULL,
  `city` varchar(50) NOT NULL,
  `phone` varchar(50) NOT NULL,
  `addressLine1` varchar(50) NOT NULL,
  `addressLine2` varchar(50),
  `state` varchar(50),
  `country` varchar(50) NOT NULL,
  `postalCode` varchar(15) NOT NULL,
  `territory` varchar(10) NOT NULL,
  PRIMARY KEY (`officeCode`) -- Constraints can also be defined this way
);
```
>- **Note that a table must have at least 1 column**

#### Describing a table
We can view a table information (Fields and their data types) by-
```
DESCRIBE `<tableName>`;
```
For example, if we wanna describe the table we just created,
```sql
Describe `offices`;
```
Output:
```sql
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| officeCode   | varchar(10) | NO   | PRI | NULL    |       |
| city         | varchar(50) | NO   |     | NULL    |       |
| phone        | varchar(50) | NO   |     | NULL    |       |
| addressLine1 | varchar(50) | NO   |     | NULL    |       |
| addressLine2 | varchar(50) | YES  |     | NULL    |       |
| state        | varchar(50) | YES  |     | NULL    |       |
| country      | varchar(50) | NO   |     | NULL    |       |
| postalCode   | varchar(15) | NO   |     | NULL    |       |
| territory    | varchar(10) | NO   |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
```

#### Inserting Data to a table
We can insert some rows into the table using the following statement.
```sql
INSERT INTO <table_name> (column1, column2, column3, ...)
VALUES (value11, value21, value31, ...) --record/row 01
	   (value12, value22, value32, ...); --record/row 02
```
> **Note that,**
- `(column1, column2, column3, ...)` is an optional list of column names within parentheses. If you specify column names, the data will be inserted into those specific columns. If you omit this list, you need to provide values for all columns in the table, and the order of values should match the table's column order.

Now let's insert some fields on our `offices` table:
```sql
INSERT INTO `offices` 

(`officeCode`,`city`,`phone`,`addressLine1`,`addressLine2`,`state`,`country`,`postalCode`,`territory`) 
VALUES ('1','San Francisco','+1 650 219 4782','100 Market Street','Suite 300','CA','USA','94080','NA'),

('2','Boston','+1 215 837 0825','1550 Court Place','Suite 102','MA','USA','02107','NA'),

('3','NYC','+1 212 555 3000','523 East 53rd Street','apt. 5A','NY','USA','10022','NA'),

('4','Paris','+33 14 723 4404','43 Rue Jouffroy D\'abbans',NULL,NULL,'France','75017','EMEA'),

('5','Tokyo','+81 33 224 5000','4-1 Kioicho',NULL,'Chiyoda-Ku','Japan','102-8578','Japan'),

('6','Sydney','+61 2 9264 2451','5-11 Wentworth Avenue','Floor #2',NULL,'Australia','NSW 2010','APAC'),

('7','London','+44 20 7877 2041','25 Old Broad Street','Level 7',NULL,'UK','EC2N 1HN','EMEA');
```

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

| Operator  | Description  |   
|-----------|--------------|
|= |Equal|
|>|Greater than|
|<|Less than|
|>=|Greater than or equal|
|<=|Less than or equal|
|<> or !=|Not equal|
|BETWEEN|Between a certain range|
|LIKE|Search for a pattern|
|IN|To specify multiple possible values for a column|

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


