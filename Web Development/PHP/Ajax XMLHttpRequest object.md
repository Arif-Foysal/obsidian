#ajax #javascript 

The `XMLHttpRequest` (often abbreviated as XHR) object is a built-in browser object that allows you to make HTTP requests to servers.

## Key Features of `XMLHttpRequest`

- **Asynchronous Communication**: `XMLHttpRequest` can send and receive data asynchronously without having to reload the entire web page. This is essential for creating dynamic, responsive web applications.
    
- **HTTP Methods**: It supports multiple HTTP methods, including `GET`, `POST`, `PUT`, `DELETE`, and others, allowing for various types of requests.
    
- **Handling Responses**: `XMLHttpRequest` can handle different types of responses, including text, JSON, and XML.
    
- **Cross-Origin Requests**: By default, `XMLHttpRequest` is subject to the same-origin policy, but it can be configured to make cross-origin requests if the server allows it (e.g., via CORS).
## Create an XMLHttpRequest Object
```js
const xhr = new XMLHttpRequest();
```



## Define a Callback Function
```js
xhr.onload = function() {  
  // What to do when the response is ready  
}
```

## Send a Request
```js
xhr.open('GET','fetch.php',true);
xhr.send();
```

## XMLHttpRequest object methods
|Method|Description|
|---|---|
|new XMLHttpRequest()|Creates a new XMLHttpRequest object|
|abort()|Cancels the current request|
|getAllResponseHeaders()|Returns header information|
|getResponseHeader()|Returns specific header information|
|open(_method, url, async, user, psw_)|Specifies the request  <br>  <br>_method_: the request type GET or POST  <br>_url_: the file location  <br>_async_: true (asynchronous) or false (synchronous)  <br>_user_: optional user name  <br>_psw_: optional password|
|send()|Sends the request to the server  <br>Used for GET requests|
|send(_string_)|Sends the request to the server.  <br>Used for POST requests|
|setRequestHeader()|Adds a label/value pair to the header to be sent|

## XMLHttpRequest object properties

| Property           | Description                                                                                                                                                                                                         |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| onload             | Defines a function to be called when the request is received (loaded)                                                                                                                                               |
| onreadystatechange | Defines a function to be called when the readyState property changes                                                                                                                                                |
| readyState         | Holds the status of the XMLHttpRequest.  <br>0: request not initialized  <br>1: server connection established  <br>2: request received  <br>3: processing request  <br>4: request finished and response is ready    |
| responseText       | Returns the response data as a string                                                                                                                                                                               |
| responseXML        | Returns the response data as XML data                                                                                                                                                                               |
| status             | Returns the status-number of a request  <br>200: "OK"  <br>403: "Forbidden"  <br>404: "Not Found"  <br>For a complete list go to the [Http Messages Reference](https://www.w3schools.com/tags/ref_httpmessages.asp) |
| statusText         | Returns the status-text (e.g. "OK" or "Not Found")                                                                                                                                                                  |
|                    |                                                                                                                                                                                                                     |
## The `onreadystatechange` property
The `readyState` property holds the status of the XMLHttpRequest.

The `onreadystatechange` property defines a callback function to be executed when the readyState changes.

The `status` property and the `statusText` properties hold the status of the XMLHttpRequest object.

| Property           | Description                                                                                                                                                                                                      |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| onreadystatechange | Defines a function to be called when the readyState property changes                                                                                                                                             |
| readyState         | Holds the status of the XMLHttpRequest.  <br>0: request not initialized  <br>1: server connection established  <br>2: request received  <br>3: processing request  <br>4: request finished and response is ready |
| status             | 200: "OK"  <br>403: "Forbidden"  <br>404: "Page not found"  <br>For a complete list go to the [Http Messages Reference](https://www.w3schools.com/tags/ref_httpmessages.asp)                                     |
| statusText         | Returns the status-text (e.g. "OK" or "Not Found")                                                                                                                                                               |
## The `onload` property
With the `XMLHttpRequest` object you can define a callback function to be executed when the request receives an answer.

The function is defined in the `onload` property of the `XMLHttpRequest` object:

```js
xhttp.onload = function() {  
  document.getElementById("demo").innerHTML = this.responseText;  
}  
xhttp.open("GET", "ajax_info.txt");  
xhttp.send();
```
## Multiple callback functions
If you have more than one AJAX task in a website, you should create one function for executing the `XMLHttpRequest` object, and one callback function for each AJAX task.
#### Step 01: Create a reusable function
```js
function ajaxRequest(url, callback) {
    var xhr = new XMLHttpRequest();
    xhr.open('GET', url, true);

    xhr.onload = function() {
        if (xhr.status >= 200 && xhr.status < 300) {
            callback(null, xhr.responseText);  // Call the callback function with the response data
        } else {
            callback('Error: ' + xhr.status);  // Call the callback function with the error
        }
    };

    xhr.onerror = function() {
        callback('Network Error');
    };

    xhr.send();
}
```

#### Step 02: Create multiple callback functions for each ajax task
```php
function displayUserInfo(error, data) {
    if (error) {
        console.error(error);
        return;
    }
    var userInfo = JSON.parse(data);
    document.getElementById('user-info').innerHTML = 
        'Name: ' + userInfo.name + '<br>' +
        'Email: ' + userInfo.email + '<br>' +
        'Age: ' + userInfo.age;
}
```

```js
function displayProducts(error, data) {
    if (error) {
        console.error(error);
        return;
    }
    var products = JSON.parse(data);
    var output = '<ul>';
    products.forEach(function(product) {
        output += '<li>' + product.name + ' - $' + product.price + '</li>';
    });
    output += '</ul>';
    document.getElementById('product-list').innerHTML = output;
}
```

#### Step 03: Execute the AJAX Requests with Different Callback Functions
Now, you can call the `ajaxRequest` function with different URLs and callback functions based on the task you need to perform.

```js
// Fetch and display user information
ajaxRequest('https://api.example.com/user-info', displayUserInfo);

// Fetch and display a list of products
ajaxRequest('https://api.example.com/products', displayProducts);
```

>Run these funcitons when an event triggers for a ajax request, for example: using onclick on a button.

## Automatically updating a section on an interval
The goal is to run the ajax function repetitively after between intervals.

If we could run the trigger for ajax req, it can be achieved

```js
// Function to initiate the periodic AJAX request
function autoUpdateUserInfo() {
ajaxRequest('fetch1.php', displayUserInfo);//the trigger function
}

// Update every 5 seconds (5000 milliseconds)
setInterval(autoUpdateUserInfo, 50);

// Initial call to update immediately when the page loads
autoUpdateUserInfo();
```
If your server responses might take a while, you could consider using `setTimeout` inside the ajax handlers to ensure that the next request only starts after the previous one finishes. This avoids potential overlap if the server is slow:
You can use `setTimeout` recursively to create a repeating action similar to `setInterval`, but with more control over the timing between executions:

```js
function autoUpdateUserInfo() {
    ajaxRequest('https://api.example.com/user-info', function(error, data) {
        displayUserInfo(error, data);

        // Schedule the next update after the current one finishes
        setTimeout(autoUpdateUserInfo, 5000);
    });
}
```

### Differences Between `setTimeout` and `setInterval`
- **`setTimeout`**: Executes the function once after the specified delay.
- **`setInterval`**: Repeatedly executes the function with a fixed time delay between each execution.









