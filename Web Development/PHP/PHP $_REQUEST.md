#PHP #superglobal 

The PHP `$_REQUEST` is a PHP superglobal variable that is used to collect the data after submitting an HTML form.

The `$_REQUEST` superglobal is an associative array which also contains the contents of [[PHP $_GET]], [[PHP $_POST]] and [[PHP $_COOKIE]] superglobals. 

**Example:**

```php
<html>
<body>

<form method="post" action="<?php echo $_SERVER['PHP_SELF'];?>"><!--Server Info--> 
  Name: <input type="text" name="fname">
  <input type="submit">
</form>

<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
  // collect value of input field
  $name = $_REQUEST['fname'];  //Using $_REQUEST Superglobal
  if (empty($name)) {
    echo "Name is empty";
  } else {
    echo $name;
  }
}
?>

</body>
</html>
```