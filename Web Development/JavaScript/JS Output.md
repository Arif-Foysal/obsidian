#javascript #webDevelopment 

## JavaScript Display Possibilities

JavaScript can "display" data in different ways:

- Writing into an HTML element, using `innerHTML`.
- Writing into the HTML output using `document.write()`.
- Writing into an alert box, using `window.alert()`.
- Writing inato the browser console, using `console.log()`.
## Using innerHTML
```js
<!DOCTYPE html>  
<html>  
<body>  
  
<h1>My First Web Page</h1>  
<p>My First Paragraph</p>  
  
<p id="demo"></p>  
  
<script>  
document.getElementById("demo").innerHTML = 5 + 6;  
</script>  
  
</body>  
</html>
```

## Using document.write()
```js
<!DOCTYPE html>  
<html>  
<body>  
  
<h1>My First Web Page</h1>  
<p>My first paragraph.</p>  
  
<script>  
document.write(5 + 6);  
</script>  
  
</body>  
</html>
```

>[!Note]
>Using document.write() after an HTML document is loaded, will **delete all existing HTML**:

```js
<!DOCTYPE html>  
<html>  
<body>  
  
<h1>My First Web Page</h1>  
<p>My first paragraph.</p>  
  
<button type="button" onclick="document.write(5 + 6)">Try it</button>  
  
</body>  
</html>
```

## Using window.alert()
You can use an alert box to display data:
```js
<!DOCTYPE html>  
<html>  
<body>  
  
<h1>My First Web Page</h1>  
<p>My first paragraph.</p>  
  
<script>  
window.alert(5 + 6);  
</script>  
  
</body>  
</html>
```
alert with click of a button-
```html
<!DOCTYPE html>
<html>
<body>

<h2>My First Web Page</h2>
<p>My first paragraph.</p>

<button onclick="window.alert(5 + 6);">click me to get alert</button>

</body>
</html> 
```

You can always skip the `window` keyword:
```js
alert("This is a alert");
```
## Using Console.log
Console.log is mostly used for debugging purposes.
```js
<!DOCTYPE html>  
<html>  
<body>  
  
<script>  
console.log(5 + 6);  
</script>  
  
</body>  
</html>
```


## JavaScript Print
JavaScript does not have any print object or print methods.
You cannot access output devices from JavaScript.
The only exception is that you can call the `window.print()` method in the browser to print the content of the current window.
```js
<!DOCTYPE html>  
<html>  
<body>  
<button onclick="window.print()">Print this page</button>  
</body>  
</html>
```
