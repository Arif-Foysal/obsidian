#PHP 

Argument aka Parameters.
PHP supports **Call by Value**, **Call by Reference**, **Default Argument Values** and **Variable-length argument**.

### 1. Call by Value

In Call by Value, the value of a variable is passed directly. This means if the value of a variable within the function is changed, it does not get changed outside of the function. 

**Example:**

```php
<?php  
function incr($i)  
{  
    $i++;  
}  
$i = 5;  
incr($i);  
echo $i;  
?>  
```
Output: 
```markup
5
```

### 2. Call by Reference

In call by reference, the address of a variable (their memory location) is passed. In the case of call by reference, we prepend an ampersand (&) to the argument name in the function definition. Any change in variable value within a function can reflect the change in the original value of a variable.

**Example:**

```php
<?php  
function incr(&$i)  
{  
    $i++;  
}  
$i = 5;  
incr($i);  
echo $i;  
?>  
```

Output: 

```markup
6
```

### 3. Default Argument Values

If we call a function without arguments, then PHP function takes the default value as an argument. 

**Example:**

```php
<?php  
function Hello($name="Aakash"){  
echo "Hello $name <br>";  
}  
Hello("Rohan");  
Hello();//passing no value  
Hello("Lovish");  
?>  
```

Output:

```markup
Hello Rohan
Hello Aakash
Hello Lovish
```
### 4. Variable Length Argument

It is used when we need to pass n number of arguments in a function. To use this, we need to write three dots inside the parenthesis before the argument. 

**Example:**

```php
<?php  
function add(...$nums) {  
    $sum = 0;  
    foreach ($nums as $n) {  
        $sum += $n;  
    }  
    return $sum;  
} 
echo add(1, 2, 3, 4);  
?>  
```

Output:

```markup
10
```


