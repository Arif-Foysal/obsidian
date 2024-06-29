#PHP 

### if-else Statement

This statement executes the block of code inside the if statement if the expression is evaluated as True and executes the block of code inside the else statement if the expression is evaluated as False. 

**Example:**

```php
<?php
$x = "22";
if ($x < "20") {
  echo "Less than 20";
} else {
  echo "Greater than 20";
}
?>
```

### Switch Statement

This statement allows us to execute different blocks of code based on different conditions. Rather than using if-elseif-if, we can use the switch statement to make our program. 

**Example:**

```php
<?php
$i = "2";
switch ($i) {
    case 0:
        echo "i equals 0";
        break;
    case 1:
        echo "i equals 1";
        break;
    case 2:
        echo "i equals 2";
        break;
    default:
       echo "i is not equal to 0, 1 or 2";
}
?>
```

