#javascript 

### **JavaScript has 8 Datatypes**

- String  
- Number  
- Bigint  
- Boolean  
- Undefined  
- Null  
- Symbol  
- Object

```js
// Numbers:  
let length = 16;  
let weight = 7.5;  
  
// Strings:  
let color = "Yellow";  
let lastName = "Johnson";  
  
// Booleans  
let x = true;  
let y = false;  
  
// Object:  
const person = {firstName:"John", lastName:"Doe"};  
  
// Array object:  
const cars = ["Saab", "Volvo", "BMW"];  
  
// Date object:  
const date = new Date("2022-03-25");
```
### **JavaScript has dynamic types**

In JavaScript, the same variable can be used to hold different data types:
```js
let x;       // Now x is undefined  
x = 5;       // Now x is a Number  
x = "John";  // Now x is a String
```
### **JS Strings**
```js
// Using double quotes:  
let carName1 = "Volvo XC60";  
  
// Using single quotes:  
let carName2 = 'Volvo XC60';
```

#### **Adding Strings to Numbers**
When adding a number and a string, JavaScript will treat the number as a string.
```js
let x = 16 + "Volvo";
```
JS will treat the above statement as follows:
```js
let x = "16" + "Volvo";
```

JavaScript evaluates expressions from left to right. Different sequences can produce different results:
```js
let x = 16 + 4 + "Volvo";
```
**result:**
```
20Volvo
```
But,
```js
let x = "Volvo" + 16 + 4;
```
**result:**
```
Volvo164
```

### **JS Numbers**
```js
// With decimals:  
let x1 = 34.00;  
  
// Without decimals:  
let x2 = 34;
```

#### **Exponential Notation**
Extra large or extra small numbers can be written with scientific (exponential) notation:
```js
let y = 123e5;    // 12300000  
let z = 123e-5;   // 0.00123
```

### **JS BigInt**

>**All JavaScript numbers are stored in a 64-bit floating-point format.**

JavaScript BigInt is a new datatype ([ES2020](https://www.w3schools.com/js/js_2020.asp)) that can be used to store integer values that are too big to be represented by a normal JavaScript Number.
```js
let x = BigInt("123456789012345678901234567890");
```
### **JS Arrays**
```js
const cars = ["Saab", "Volvo", "BMW"];

[Try it Yourself »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_array)
```

### **JS Objects**
[[JS Objects]]
The object data type can contain both **built-in objects**, and **user defined objects**:
Built-in object types can be:
objects, arrays, dates, maps, sets, intarrays, floatarrays, promises, and more.

```js
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};  
```

### **The typeof Operator**
You can use the JavaScript `typeof` operator to find the type of a JavaScript variable.
```js
typeof "John"         // Returns "string"
typeof 314            // Returns "number"
let car;    // Value is undefined, type is undefined
```
>**Any variable can be emptied, by setting the value to `undefined`. The type will also be `undefined`.**

