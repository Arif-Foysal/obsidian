There are three types of SQL statements:

**1. Data Definition Language(DDL):** The Data Definition Language contains commands that are less frequently used. DDL commands modify the actual structure of a database, rather than the database’s contents. example:

- Generating a table
- Modifying a structure of a table (altering)
[[Query Processor]] interprets DDL commands into [[low level language | low level instructions]]

**2. Data Control Language(DCL):** The Data Control Language allows you to manipulate and manage user access rights on database objects. It consists of two commands:

- the GRANT command, used to add database permissions for a user,
- and the REVOKE command, used to remove existing permissions.

These two commands form the core of the relational database security model.

**3. Data Manipulation Language (DML):** Data Manipulation Language contains the subset of SQL commands used most frequently. It is used for searching, inserting, updating, and deleting data that we will see in this notebook.

Some quick notes on the SQL syntax:

- SQL is case insensitive. You can type statements in upper case, lowercase or a mixture of both
- Database names can be typed with or without backquotes i.e. `classicmodels` or `` `classicmodels` ``
- SQL statement can span over multiple lines and must end with a semicolon `;`
- The statements in this tutorial can be executed on the MySQL command line or the workbench

The SQL syntax for each relational database software package is slightly different. Check the official documentation of your DB for details.
DML Compiler converts the DML to [[low level language]]
