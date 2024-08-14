#PHP #superglobal 

`$_GET` contains an array of variables received via the HTTP GET method.

Ways to send variables via HTTP GET method:
- Query strings in the URL
- HTML Forms
## Query string in the URL

A query string is data added at the end of a URL. In the link below, everything after the `?` sign is part of the query string:

```html
<a href="demo_phpfile.php?subject=PHP&web=W3schools.com">Test $GET</a>
```

The query string above contains two key/value pairs:

```html
subject=PHP
web=W3schools.com
```

In the PHP file we can use the `$_GET` variable to collect the value of the query string.

**demo_phpfile.php** :
```php
<html>
<body>

<?php
echo "Study " . $_GET['subject'] . " at " . $_GET['web'];
?>

</body>
</html>
```


