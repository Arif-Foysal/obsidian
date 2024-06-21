#javascript 

> **In JavaScript, Objects are King.**
> **If you Understand Objects, you Understand JavaScript.**

JavaScript Objects are variables too. But objects can contain many values.

```js
const person = {  
  firstName: "John",  
  lastName : "Doe",  
  id       : 5566,  
  fullName : function() {  
    return this.firstName + " " + this.lastName;  
  }  
};
```


>**It is a common practice to declare a variable with** [[JS Variables#**JavaScript Const**|const]] **keyword.**


### **Defining Objects**

See [[C++ variable declarations and definitions]]

**3 Ways:**
- Using an Object Literal
- Using the `new` Keyword
- Using an Object Constructor
#### **JS Object Literal**
An object literal is a list of **name:value** pairs inside curly braces **{}**.
```js
{firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}
```

```js
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};  
```
For readability:
```js
// Create an Object  
const person = {  
  firstName: "John",  
  lastName: "Doe",  
  age: 50,  
  eyeColor: "blue"  
};
```

**Creating JS object, then adding properties:**
```js
// Create an Object  
const person = {};  
  
// Add Properties  
person.firstName = "John";  
person.lastName = "Doe";  
person.age = 50;  
person.eyeColor = "blue";
```

#### **`new` Keyword**
```js
// Create an Object  
const person = new Object();  
  
// Add Properties  
person.firstName = "John";  
person.lastName = "Doe";  
person.age = 50;  
person.eyeColor = "blue";
```
>[!Note]
>The examples above do exactly the same.
But, there is no need to use `new Object()`.
For readability, simplicity and execution speed, use the **object literal** method.

### Accessing Object Properties

```
objectName.propertyName
```
or
```
objectName["propertyName"]
```

For example:
```js
person.lastName;
person["lastName"]; //will give the same result
```

### JS Object Methods

```js
const person = {  
  firstName: "John",  
  lastName : "Doe",  
  id       : 5566,  
  fullName : function() {  
    return this.firstName + " " + this.lastName;  
  }  
};
```

![[JS Primitives]]

