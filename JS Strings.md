!! Incomplete

>**Note:** Strings are immutable, meaning strings cannot be changed, they can only be replaced.

Zero or more characters written inside quotes.
```js
let text = “John Doe”;
```
You can use both single and double quotes.
```js
let name1 = “sabila”;
let name2 = ‘nabila’;
```
>But watch out when you’re using quotes inside quotes
```js
let answer1 = "It's alright";  
let answer2 = "He is called 'Johnny'";  
let answer3 = 'He is called "Johnny"';
```
You can also use escape characters to solve this problem:
### Escape characters:
| Code | Result | Description  |
| ---- | ------ | ------------ |
| `\'` | '      | Single quote |
| `\"` | "      | Double quote |
| `\\` | \|     | Backslash    |
Example:
```js
let text = "We are the so-called \"Vikings\" from the north.";
```

Six other escape sequences are valid in JavaScript:

| Code | Result               |
| ---- | -------------------- |
| `\b` | Backspace            |
| `\f` | Form Feed            |
| `\n` | New Line             |
| `\r` | Carriage Return      |
| `\t` | Horizontal Tabulator |
| `\v` | Vertical Tabulator   |

### Template strings:
We can have both single and double quotes in a string using template string(ES6). Template strings enclosed in backticks.

```js
let text = `He’s often called “Johnny”`;
```
>Not supported in internet explorer.

### String methods

>All string methods return a new string. They do not modify the original one.
#### String length
##### `length`
Returns length of a string
```js
let text = “ABCDEFGH”;
let len = text.length; //returns length of string
```
#### Returning indexed string characters
There are 4 methods for extracting string characters:

- The `at(_position_)` Method
- The `charAt(_position_)` Method
- The `charCodeAt(_position_)` Method
- Using property access [] like in arrays
##### `at()`
Returns indexed character from a string.
```js
let text = ‘United’;
let char = text.at(0);
console.log(char);
```
Output:
`U`
>Will return `undefined` if index out of bound.

Like python, it will give the last element if index is `-1` and so on.

Similar thing can be done by bracket notation:
```js
Let char = text[0];
```
`charAt()` works as the same as `at()`
##### `charCodeAt()`
The `charCodeAt()` method returns the code of the character at a specified index in a string. The method returns a UTF-16 code (an integer between 0 and 65535).
```js
let text = "HELLO WORLD";  
let char = text.charCodeAt(0);
```
Output:
```
72
```
#### Extracting string parts
There are 3 methods for extracting a part of a string:

- `slice(_start_, _end_)`
- `substring(_start_, _end_)`
- `substr(_start_, _length_)`
##### Using `slice()`
extracts a part of a string and returns the extracted part in a new string.

```js
let text = "Apple, Banana, Kiwi";  
let part = text.slice(7, 13);
```
Output:
`Banana`

The method takes 2 parameters: start position, and end position.
>Start included, end not included.

If you omit the second parameter, the method will slice out the rest of the string:
```js
let text = "Apple, Banana, Kiwi";  
let part = text.slice(7);
```
Output:
`Banana, Kiwi`

This example slices out a portion of a string from position -12 to position -6: 
```js
let text = "Apple, Banana, Kiwi";  
let part = text.slice(-12, -6);
```
Output:
`Banana`

##### Using `substring()`
`substring()` is similar to `slice()`.

The difference is that start and end values less than 0 are treated as 0 in `substring()`.

```js
let str = "Apple, Banana, Kiwi";  
let part = str.substr(7);
```
Output: `Banana, Kiwi`
```js
let str = "Apple, Banana, Kiwi";  
let part = str.substr(-4);
```
Output: `Kiwi`

#### Converting to upper and lower case
Convert string to Uppercase- `toUpperCase()`
```js
let txt1 = “Hello World”;
let txt2 = txt1.toUpperCase();
```
Convert string to Lowercase- `toLowerCase()`
```js
let txt1 = “Hello World”;
let txt2 = txt1.toLowerCase();
```

#### Concatenating to string:
##### Using `concat()`
```js
text = "Hello" + " " + "World!";  
text = "Hello".concat(" ", "World!");
```
- [ ] learn how to do it with backticks.
#### Removing whitespaces 

```js
let text1 = "      Hello World!      ";  
let text2 = text1.trim();
```
Removing spaces only from beginning:
```js
let text1 = "     Hello World!     ";  
let text2 = text1.trimStart();
```
Removing spaces only from end:
```js
let text1 = "     Hello World!     ";  
let text2 = text1.trimEnd();
```
#### Add padding to a string
The `padStart()` method pads a string from the start.

It pads a string with another string (multiple times) until it reaches a given length.
```js
let text = "5";  
let padded = text.padStart(4,"0");
```
The above example Pad a string with "0" until it reaches the length 4.
#### Repeating a string
The `repeat()` method returns a string with a number of copies of a string.
```js
let text = "Hello world!";  
let result = text.repeat(2);
```
Output: `Hello world!Hello world!`

#### Replacing String content
The `replace()` method replaces a specified value with another value in a string:
```js
let text = "Please visit Microsoft!";  
let newText = text.replace("Microsoft", "W3Schools");
```
It is case sensitive by default, To replace case insensitive, use a **regular expression** with an `/i` flag (insensitive):
```js
let text = "Please visit Microsoft!";  
let newText = text.replace(/MICROSOFT/i, "W3Schools");
```

>it replaces only the first match. 
>To replace all occurrences, you can use while loop. You know what to do. Or you can use [[JS Regular Expressions]], just as belows:
```js
let text = "Please visit Microsoft and Microsoft!";  
let newText = text.replace(/Microsoft/g, "W3Schools");
```

In 2021, JavaScript introduced the string method `replaceAll()`:
```js
text = text.replaceAll("Cats","Dogs");  
text = text.replaceAll("cats","dogs");
```
The `replaceAll()` method allows you to specify a regular expression instead of a string to be replaced.

If the parameter is a regular expression, the global flag (g) must be set, otherwise a TypeError is thrown.
```js
text = text.replaceAll(/Cats/g,"Dogs");  
text = text.replaceAll(/cats/g,"dogs");
```
#### Converting string to array
Using `split()`
```js
text.split(",")    // Split on commas  
text.split(" ")    // Split on spaces  
text.split("|")    // Split on pipe
```
For example:
```js
let text = "a,b,c,d,e,f";
const myArray = text.split(",");
```
myarray will be an array containing:
```
[‘a’, ‘b’, ‘c’, ‘d’, ‘e’, ‘f’]
```
If the separator is omitted, the returned array will contain the whole string in index `[0]`.

If the separator is "", the returned array will be an array of single characters.

### Searching on string




**Ref:** https://www.w3schools.com/jsref/jsref_obj_string.asp