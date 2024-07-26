#javascript 

```js
switch (new Date().getDay()) {  
  case 0:  
    day = "Sunday";  
    break;  
  case 1:  
    day = "Monday";  
    break;  
  case 2:  
     day = "Tuesday";  
    break;  
  case 3:  
    day = "Wednesday";  
    break;  
  case 4:  
    day = "Thursday";  
    break;  
  case 5:  
    day = "Friday";  
    break;  
  case 6:  
    day = "Saturday";  
}
```
When JavaScript reaches a `break` keyword, it breaks out of the switch block.

This will stop the execution inside the switch block.

It is not necessary to break the last case in a switch block. The block breaks (ends) there anyway.

The `default` keyword specifies the code to run if there is no case match.

## Common Code Blocks

Sometimes you will want different switch cases to use the same code.

In this example case 4 and 5 share the same code block, and 0 and 6 share another code block:

```js
switch (new Date().getDay()) {  
  case 4:  
  case 5:  
    text = "Soon it is Weekend";  
    break;   
  case 0:  
  case 6:  
    text = "It is Weekend";  
    break;  
  default:   
    text = "Looking forward to the Weekend";  
}
```

- If multiple cases matches a case value, the **first** case is selected.

- If no matching cases are found, the program continues to the **default** label.

- If no default label is found, the program continues to the statement(s) **after the switch**.

