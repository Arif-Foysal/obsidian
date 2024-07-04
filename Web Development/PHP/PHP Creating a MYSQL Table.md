#PHP #MySQL 

Let's create a simple table "Employees", consisting of five columns: "employeeID", "firstname", "lastname", "email" and "joining_date".
### **The query:**
The [[SQL]] query looks something like this:
```sql
CREATE TABLE Employees(
employeeID INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
firstname VARCHAR(30) NOT NULL,
lastname VARCHAR(30) NOT NULL,
email VARCHAR(50),
joining_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)
```

Let's break down the attributes:

- NOT NULL - Each row must contain a value for that column, null values are not allowed.
- DEFAULT value - Set a default value that is added when no other value is passed.
- UNSIGNED - Used for number types. It limits the stored data to positive numbers and zero.
- AUTO INCREMENT - MySQL automatically increases the value of the field by 1 each time a new record is added.
- PRIMARY KEY - Used to uniquely identify the rows in a table.

```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "cwhDB";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}

// sql to create table
$sql = "CREATE TABLE Employees(
employeeID INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
firstname VARCHAR(30) NOT NULL,
lastname VARCHAR(30) NOT NULL,
email VARCHAR(50),
joining_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)";

if ($conn->query($sql) === TRUE) {
  echo "Table Employees created successfully";
} else {
  echo "Error creating table: " . $conn->error;
}

$conn->close();
?>
```
