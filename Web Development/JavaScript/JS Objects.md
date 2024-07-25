#javascript 

>[!Links]
>- [[JS Objects#**Defining Objects**|Defining Objects]]
>- [[JS Objects#Accessing Object Properties|Accessing Object Properties]]
>- [[JS Objects#JS Object Methods|Object Methods]]

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

```js
//objectName.propertyName
let age = person.age;
```
or
```js
//objectName["propertyName"]
let name = person[“name”];
```

For example:
```js
person.lastName;
person["lastName"]; //will give the same result
```

#### **Adding new properties:**
You can add new properties to an existing object by simply giving it a value:
```js
Person.nationality = “English”;
```
#### Adding new methods:

```js
person.name = function () {  
  return this.firstName + " " + this.lastName;  
};
```
#### **Deleting properties**
Using the `delete` keyword:
```js
delete person.age;
```
#### **Nested Objects:**
Property values can be other objects:
```js
myObj = {  
  name:"John",  
  age:30,  
  myCars: {  
    car1:"Ford",  
    car2:"BMW",  
    car3:"Fiat"  
  }  
}
```
You can access them using dot notation or bracket notation:
```js
let car3 = MyObj.myCars.car3;
```
Or,
```js
let car3 = MyObj[myCars][car3];
```
#### Displaying Object Properties
##### Using Loops
```js
const person = {  
  name: "John",  
  age: 30,  
  city: "New York"  
};  
  
// Build a Text  
let text = "";  
for (let x in person) {  
  text += person[x] + " ";  
};  
  
// Display the Text  
document.getElementById("demo").innerHTML = text;
```
Output:
```
John 30 New York
```
>You must use `person[x]` in the loop. `person.x` will not work, because x is the loop variable.

##### Using Object.values()
`Object.values()` creates an [[JS Data Types#**JS Arrays**|JS Array]] from the property values:
```js
// Create an Object  
const person = {  
  name: "John",  
  age: 30,  
  city: "New York"  
};  
  
// Create an Array  
const myArray = Object.values(person);  
  
// Display the Array  
document.getElementById("demo").innerHTML = myArray;
```

##### Using Object.entries()
`Object.entries()` makes it simple to sue objects in loops:
```js
const fruits = {Bananas:300, Oranges:200, Apples:500};  
  
let text = "";  
for (let [fruit, value] of Object.entries(fruits)) {  
  text += fruit + ": " + value + "<br>";  
}
```
##### Using JSON.stringify()
JS objects can be converted to a string with [[JSON]] method `JSON.stringify()`. The result will be a string written in a JSON notation:
```js
// Create an Object  
const person = {  
  name: "John",  
  age: 30,  
  city: "New York"  
};  
  
// Stringify Object  
let myString = JSON.stringify(person);  
  
// Display String  
document.getElementById("demo").innerHTML = myString;
```

### JS Object Methods
Object methods are actions that can be performed on Objects.
```js
const person = {  
  firstName: "John",  
  lastName : "Doe",  
  id       : 5566,  
  fullName : function() {  //function/method definition
    return this.firstName + " " + this.lastName;  
  }  
};
```
#### Calling object methods:
```js
let fullname = person.fullName();
```
>Note: if you call a method without `()`, it will return the **function definition.**



In JS, all values are an object. Except [[JS Primitives]].

![[JS Primitives]]

### **JS Object Constructors:**
JS object constructors are similar as `classes` in [[object-oriented-programming]] languages.
Object constructors in JS is basically used when we need to create many objects of the same type.

>Note: It is a good practice to name constructor functions with an upper-case first letter.

**First, we need to define the constructor:**
```js
function Person(first, last, age, eye) {  
  this.firstName = first;  
  this.lastName = last;  
  this.age = age;  
  this.eyeColor = eye;  
}
```
>In this constructor function, `this` has no value. The value of `this` will become the new object when a new object is created.

Now, we can use `new Person()` to create many new Person objects:
```js

const myFather = new Person("John", "Doe", 50, "blue");  
const myMother = new Person("Sally", "Rally", 48, "green");  
const mySister = new Person("Anna", "Rally", 18, "green");  
  
const mySelf = new Person("Johnny", "Rally", 22, "green");
```
#### Property default values:
A value given to a property will be a default value for all objects created by the constructor:

```js

function Person(first, last, age, eyecolor) {  
  this.firstName = first;  
  this.lastName = last;  
  this.age = age;  
  this.eyeColor = eyecolor;  
  this.nationality = "English";  
}
```

#### Adding a property to an Object
To add a new property to a created object:
```js
myFather.language = "Bengali";
```
#### Adding a property to a Constructor:
You can not add a new property to an object constructor, for instance, you can **not** do this:
```js
Person.job=“Teacher”;
```
This will not work.
To add a new property, you must add it to the constructor function prototype:
```js
Person.prototype.job = “Teacher”;
```
#### Constructor function methods:
A constructor function can also have methods:
```js
function Person(first, last, age, eyecolor) {  
  this.firstName = first;  
  this.lastName = last;  
  this.age = age;  
  this.eyeColor = eyecolor;  
  this.fullName = function() {  
    return this.firstName + " " + this.lastName;  
  };  
}
```
#### Adding new method to a Constructor:
You cannot add a new method to an object constructor function, this will give an error:
```js
Person.changeName = function (name) {  
  this.lastName = name;  
}  
  
myMother.changeName("Doe");
```
Adding a method is also done to the constructor function prototype:
```js
Person.prototype.changeName = function (name) {  
  this.lastName = name;  
}  
  
myMother.changeName("Doe");
```

#### Built in JS constructors:
```js
new Object()   // A new Object object  
new Array()    // A new Array object  
new Map()      // A new Map object  
new Set()      // A new Set object  
new Date()     // A new Date object  
new RegExp()   // A new RegExp object  
new Function() // A new Function object
```
Facts:
- Use object literals `{}` instead of `new Object()`
- Use array literals `[]` instead of `new Array()`
- Use pattern literals `/()/` instead of `new RegExp()`.
- Use function expressions `() {}` instead of `new Function()`.

### **JS Objects are Mutable**
Objects are mutable, they are addressed by reference, not by value.
If person is an object, the following statement will not create a copy of person:
```js
const x = person;
```
The object x is not a copy of person. X refers to person, meaning any changes to x will also change person:
```js
//Create an Object  
const person = {  
  firstName:"John",  
  lastName:"Doe",  
  age:50, eyeColor:"blue"  
}  
  
// Create a copy  
const x = person;  
  
// Change Age in both  
x.age = 10
```

