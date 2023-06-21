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
