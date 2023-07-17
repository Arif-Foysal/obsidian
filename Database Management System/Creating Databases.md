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
