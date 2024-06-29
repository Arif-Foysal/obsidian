#PHP 

**In PHP, we have the following loops:**

1. while Loop
2. do-while Loop
3. for Loop
4. foreach loop

### 1. While Loop

The While loop in PHP is used when we need to execute a block of code again and again based on a given condition. If the condition never becomes false, the while loop keeps getting executed. Such a loop is known as an infinite loop. 

**Example:**

```php
<?php
$x = 1;
while($x <= 10) {
  echo "The number is: $x <br>";
  $x++;
}
?>
```

### 2. Do-While Loop

The do-while loop is similar to a while loop except that it is **guaranteed to execute at least once**. After executing a part of a program for once, the rest of the code gets executed based on a given boolean condition.

**Example:**

```php
<?php
$x =10;
do {
  echo "The number is: $x <br>";
  $x++;
} while ($x <= 9);
?>
```


### 3. For Loop

The for loop is used to iterate a block of code multiple times. 

**Example:**

```php
<?php
for ($x = 0; $x <= 10; $x++) {
  echo "The number is: $x <br>";
}
?>
```

### 4. Foreach loop

The foreach loop in PHP can be used to access the array indexes in PHP. It only works on arrays and objects. 

**Example:**

```php
<?php
echo "Welcome to the world of foreach loops <br>";
$arr = array("Bananas", "Apples", "Harpic", "Bread", "Butter");
foreach ($arr as  $value) {
    echo "$value <br>";
}
?>
```