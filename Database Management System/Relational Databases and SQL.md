**What is a Database?**
A database is an organized collection of structured information, typically stored in the form of tables (rows & columns). Relational databases allow storing and retrieving different kinds of related information e.g. products, customers, and orders for an online shopping site. Structured Query Language or SQL (pronounced "sequel") is the most widely used language for interacting with relational databases, and is an essential skill for Data Science professionals.

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


**References**
[Relation Databases-Jovian](https://jovian.com/aakashns/relational-databases-and-sql)


