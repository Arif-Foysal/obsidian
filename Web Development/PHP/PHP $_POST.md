#PHP #superglobal 

`$_POST` is A superglobal associative array in PHP used to collect form data sent with the POST method.

**Example:**
First, create an HTML form that uses the POST method:
```html
<!DOCTYPE html>
<html>
<body>

<form method="post" action="process_form.php">
  Name: <input type="text" name="name"><br>
  Email: <input type="text" name="email"><br>
<input type="submit" value="Submit"> //don't panic, it's just a button, a tiny one.
</form>

</body>
</html>
```

- The `method="post"` attribute specifies that the form data should be sent using the POST method.
- The `action="process_form.php"` attribute specifies the file (`process_form.php`) that will handle the form submission.

**The PHP script `process_form.php`**
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Collect value of input field
    $name = $_POST['name']; //this is what you've gussed
    $email = $_POST['email'];

    if (empty($name) || empty($email)) {
        echo "Name and email are required!";
    } else {
        echo "Name: " . htmlspecialchars($name) . "<br>";
        echo "Email: " . htmlspecialchars($email);
    }
}
?>
```

### **Another example:**

**`htmlentities()` Function:** The `htmlentities()` function is an inbuilt function that is used to transform all characters which are applicable to HTML entities.

**Example:**
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
$name = htmlspecialchars($_REQUEST['fname']); //Collecting Value
if (empty($name)) {
echo "Empty Name";
} else {
echo $name;
}
}
?>
```

