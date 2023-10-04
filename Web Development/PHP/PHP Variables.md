#PHP #webDevelopment 

>[!Contents]
>- [[PHP Variables#PHP Variables|PHP Variables]]
>- [[PHP Variables#PHP Variables Scope|PHP Variables Scope]]
## PHP Variables
### Declaring PHP variables
starts with the `$` sign, followed by the name of the variable:
```php
<?php  
$txt = "Hello world!";  
$x = 5;  
$y = 10.5;  
?>
```
### Rules for PHP variables
Rules for PHP variables:
- A variable starts with the `$` sign, followed by the name of the variable
- A variable name must start with a letter or the underscore character
- A variable name cannot start with a number
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Variable names are case-sensitive (`$age` and `$AGE` are two different variables)
### Outputting a variable
```php
<?php  
$txt = "W3Schools.com";  
echo "I love $txt!";  
?>
```
or
```php
<?php  
$txt = "W3Schools.com";  
echo "I love " . $txt . "!";  
?>
```
or
```php
<?php  
$txt = "W3Schools.com";  
echo "I love ", $txt , "!";  
?>
```

>[!note]
>PHP is loosely typed language, meaning we do not have to tell PHP which data type the variable is
## PHP Variables Scope
The scope of a variable is the part of the script where we can use/refer the variable.
PHP has three different variable scopes:

- local
- global
- static
### Global and Local Variables
A variable declared **outside** a function has a GLOBAL SCOPE and can only be accessed outside a function:
```php
<?php  
$x = 5; // global scope  
  
function myTest() {  
  // using x inside this function will generate an error  
  echo "<p>Variable x inside function is: $x</p>";  
}  
myTest();  
  
echo "<p>Variable x outside function is: $x</p>";  
?>
```

A variable declared **within** a function has a LOCAL SCOPE and can only be accessed within that function:
```php
<?php  
function myTest() {  
  $x = 5; // local scope  
  echo "<p>Variable x inside function is: $x</p>";  
}  
myTest();  
  
// using x outside the function will generate an error  
echo "<p>Variable x outside function is: $x</p>";  
?>
```
>[!note]
>You can have local variables with the same name in different functions, because local variables are only recognized by the function in which they are declared.

### The global Keyword in PHP

The `global` keyword is used to access a global variable from within a function.
To do this, use the `global` keyword before the variables (inside the function):
```php
<?php  
$x = 5;  
$y = 10;  
  
function myTest() {  
  global $x, $y;  
  $y = $x + $y;  
}  
  
myTest();  
echo $y; // outputs 15  
?>
```

PHP also stores all global variables in an array called `$GLOBALS[_index_]`. The _`index`_ holds the name of the variable. This array is also accessible from within functions and can be used to update global variables directly.
```php
<?php  
$x = 5;  
$y = 10;  
  
function myTest() {  
  $GLOBALS['y'] = $GLOBALS['x'] + $GLOBALS['y'];  
}  
  
myTest();  
echo $y; // outputs 15  
?>
```

### The Static keyword in PHP
Normally, when a function is completed/executed, all of its variables are deleted. However, sometimes we want a local variable NOT to be deleted. We need it for a further job.

To do this, use the `static` keyword when you first declare the variable:
```php
<?php  
function myTest() {  
  static $x = 0;  
  echo $x;  
  $x++;  
}  
  
myTest();  
myTest();  
myTest();  
?>
```
The output will be-
```
0
1
2
```
>[!Note]
>We are only assigning the value in the first time we're calling the function. Next time we call the function, the variable will hold the value from the last call.

