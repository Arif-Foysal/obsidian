#javascript 

>[!Links]
>- [[JS Primitives]]


**JavaScript Variables can be declared in 4 ways:**
- Automatically (kinda like python)
- Using `var`
- Using `let`
- Using `const`

> The `var` keyword should only be used in code written for older browsers.

### **When to use var, let and const**

1. Always declare variables
2. Always use `const` if the value should not be changed
3. Always use `const` if the type should not be changed (Arrays and Objects)
4. Only use `let` if you can't use `const`
5. Only use `var` if you MUST support old browsers.
6. `var` is [[hoisting|hoisted]].
### **JavaScript Let**
- Variables declared with `let` have **Block Scope**
- Variables declared with `let` must be **Declared** before use
- Variables declared with `let` cannot be **Redeclared** in the same scope
#### **Block scope in JS**
>[!Fact]
>Before ES6 (2015), JavaScript did not have **Block Scope**.
Back then, JavaScript had **Global Scope** and **Function Scope**.

Variables declared inside a { } block cannot be accessed from outside the block:
```js
{  
  let x = 2;  
}  
// x can NOT be used here
```

#### **Var is always global**
Variables declared with the `var` always have **Global Scope**.
Variables declared with the `var` keyword can NOT have block scope:
```js
{  
  var x = 2;  
}  
// x CAN be used here
```

### **JavaScript Const**
**When to use??**
Always declare a variable with `const` when you know that the value should not be changed.
Use `const` when you declare:
- A new Array
- A new Object
- A new Function
- A new RegExp
#### **Constant Objects and Arrays**
The keyword `const` is a little misleading.
It does not define a constant value. It defines a constant reference to a value.

Because of this you can NOT:
- Reassign a constant value
- Reassign a constant array
- Reassign a constant object

But you CAN:
- Change the elements of constant array
- Change the properties of constant object

#### **Constant arrays**

You can not reassign constant array
```js
const cars = ["Saab", "Volvo", "BMW"];  
cars = ["Toyota", "Volvo", "Audi"];    // ERROR
```

But you can change elements of constant array
```js
// You can create a constant array:  
const cars = ["Saab", "Volvo", "BMW"];  
  
// You can change an element:  
cars[0] = "Toyota";  

// You can add an element:  
cars.push("Audi");
```

#### **Constant objects**
Learn more about [[JS Objects]]

You can change the properties of a constant object:
```js
// You can create a const object:  
const car = {type:"Fiat", model:"500", color:"white"};  
  
// You can change a property:  
car.color = "red";  
  
// You can add a property:  
car.owner = "Johnson";
```

But you can NOT reassign the object:
```js
const car = {type:"Fiat", model:"500", color:"white"};  
  
car = {type:"Volvo", model:"EX60", color:"red"};    // ERROR
```

![[JS Primitives]]