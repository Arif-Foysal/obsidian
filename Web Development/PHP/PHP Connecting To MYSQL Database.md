#PHP #MySQL 

**There are two types of approaches:**
1. mysqli Object-Oriented Method
2. Procedural Method

### **Object Oriented Method:**

```php
<?php
$servername = "localhost";
$username = "root";
$password = "";

// Creating a connection
$conn = new mysqli($servername, $username, $password);

// Checking the connection
if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully";
?>
```

### **Procedural Method:**
```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";

// Create a connection
$conn = mysqli_connect($servername, $username, $password);

// Check the connection
if (!$conn) {
  die("Connection failed: " . mysqli_connect_error());
}
echo "Connected successfully";
?>
```

**Learn more about the mysqli class:** https://www.php.net/manual/en/class.mysqli.php