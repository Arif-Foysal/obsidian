#PHP #webDevelopment 

`echo` and `print` are more or less the same. They are both used to output data to the screen.
The differences are small: `echo` has no return value while `print` has a return value of 1 so it can be used in expressions. `echo` can take multiple parameters (although such usage is rare) while `print` can take one argument.

The `echo` and `print` statement can be used with or without parentheses: `echo` or `echo()` and `print` or `print()`
## PHP echo Statement


>[!Note]
>echo statement can contain HTML elements

**Displaying Text**
```php
<?php  
echo "<h2>PHP is Fun!</h2>";  
echo "Hello world!<br>";  
echo "I'm about to learn PHP!<br>";  
echo "This ", "string ", "was ", "made ", "with multiple parameters.";  
?>
```

**Displaying Variables**
![[PHP Variables#Outputting a variable]]

## PHP print Statement

**Displaying Text**
```php
<?php  
echo "<h2>PHP is Fun!</h2>";  
echo "Hello world!<br>";  
echo "I'm about to learn PHP!<br>";  
echo "This ", "string ", "was ", "made ", "with multiple parameters.";  
?>
```

**Displaying Variables**

```php
<?php  
$txt1 = "Learn PHP";  
$txt2 = "W3Schools.com";  
$x = 5;  
$y = 4;  
  
echo "<h2>" . $txt1 . "</h2>";  
echo "Study PHP at " . $txt2 . "<br>";  
echo $x + $y;  
?>
```



