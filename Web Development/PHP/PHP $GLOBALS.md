#PHP #superglobal

`$GLOBALS` is a [[PHP Superglobals|superglobal]] variable which is also an array that stores all the [[PHP Variables#PHP Variables Scope#Global and Local Variables|global]] variables and is used to access global variables from anywhere in the PHP program. 

**Example:**

```php
<?php
$x = 10;
$y = 11;
 
function add() {
  $GLOBALS['z'] = $GLOBALS['x'] + $GLOBALS['y'];
}
 
add();
echo $z;
?>
```

**Output:**

```php
21
```

