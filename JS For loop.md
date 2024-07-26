#javascript 

```js
for (let i = 0; i < 5; i++) {  
  console.log(i);  
}
```
Syntax:
```
for (expression 1; expression 2; expression 3) {  
  // code block to be executed  
}
```
**Expression 1** is executed (one time) before the execution of the code block. (expression 1 is optional)

**Expression 2** defines the condition for executing the code block.(also optional)

**Expression 3** is executed (every time) after the code block has been executed.(this is also optional. And It’s crazy)

# Expression 1:
You can initiate multiple values in expression 1:
```js

for (let i = 0, len = cars.length, text = ""; i < len; i++) {   
  text += cars[i] + "<br>";  
}
```
## Omitting expression 1 

```js
let i = 2;  
let len = cars.length;  
let text = "";  
for (; i < len; i++) {   
  text += cars[i] + "<br>";  
}
```
# Expression 2:
As expression 2 is optional, you can omit this expression.
But,

>If you omit expression 2, you must provide a **break** inside the loop. Otherwise the loop will never end. This will crash your browser. Read about breaks in a later chapter of this tutorial.

# Expression 3:

# Loop scopes

### Using `var` in loop

```js
var i = 5;  
  
for (var i = 0; i < 10; i++) {  
  // some code  
}  
  
// Here i is 10
```
### Using `let` in loop
```js
let i = 5;  
  
for (let i = 0; i < 10; i++) {  
  // some code  
}  
  
// Here i is 5
```

