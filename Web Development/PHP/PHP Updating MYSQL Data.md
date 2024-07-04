#PHP #MySQL 

[[SQL]]

Updating data in MySQL is very easy with the UPDATE statement. Let's assume we have this table where we need to update the lastname of the second employee. 

|   |   |   |   |   |
|---|---|---|---|---|
|employeeID|firstname|lastname|email|joining_date|
|1|Harry|Bhai|harrybhai@bhai.com|2022-11-04 14:54:58|
|2|Rohan|Das|rohanbhai@bhai.com|2022-11-04 15:44:51|

To update the lastname in the Employees table we will use the **UPDATE** command along side **SET** command and **WHERE** command. The **SET** command assigns variables and the **WHERE** command specifies which record should be updated. 

**Note:** If we don't use the **WHERE** clause, then all records will be updated.

```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "cwhDB";

// Create a connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check the connection
if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}

$sql = "UPDATE Employees SET lastname='Bhai' WHERE id=2";

if ($conn->query($sql) === TRUE) {
  echo "Record updated successfully";
} else {
  echo "Error updating record: " . $conn->error;
}

$conn->close();
?>
```
