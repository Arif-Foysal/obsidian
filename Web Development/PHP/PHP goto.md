#PHP 

[[c++ goto]]

```php
for($i = 1; $i <=10; $i++){
	if($i == 3){
		goto statement1; //jumps to the given statement.
	}
	echo $i;
	<br>
}
echo "hello there";
statement1:
	echo "this is fun";
```
Output:
```
1
2
this is fun
```


```php
<?php

echo "This is the first line.\n";

goto skip;  // Jump to the 'skip' label

echo "This line will be skipped.\n"; // This line is not executed

skip:  // Label where the code jumps
echo "This is the line after the skip.\n";

?>

```

Output:
```
This is the first line.
This is the line after the skip.
```


### Use Cases:

`goto` can be useful in situations where you need to break out of deeply nested loops or switch cases, but it's typically better to use structured control flow (like loops, functions, or exceptions) for readability and maintainability.

### Important Notes:

- Labels must be unique within the scope of a script.
- Overusing `goto` can lead to "[[spaghetti code]]," making your code difficult to follow.
