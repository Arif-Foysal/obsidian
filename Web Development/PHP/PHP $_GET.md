#PHP #superglobal 

The PHP `$_GET` is a PHP superglobal which is used to collect form data after submitting an HTML form using method="get". Information sent from an HTML form with the GET method is displayed in the browser's address bar making it less secure than [[PHP $_POST]].

Let's assume we have a HTML form that takes name and email as an input and sends it to anothe file named "name_get.php". We can access the values of "name_get.php" with $_GET superglobal.

**HTML FORM**

```html
<html>
<body>

<form action="name_get.php" method="get">
Name: <input type="text" name="name">
Email: <input type="text" name="email">
<input type="submit">
</form>

</body>
</html> 
```

**name_get.php**

```php
<html>
<body>

Welcome <?php echo $_GET["name"]; ?>!
Your email address is <?php echo $_GET["email"]; ?>

</body>
</html> 
```

**Output:**

```markdown
Welcome Harry!
Your email address is harry@example.com
```
