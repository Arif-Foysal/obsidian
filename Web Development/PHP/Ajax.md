>[!Links] 
>- [[HTML Status Codes]]
>- [[XMLHttpRequest readyState property]]
>


AJAX is about updating parts of a web page, without reloading the whole page.
AJAX allows web pages to be updated asynchronously by exchanging small amounts of data with the server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

![[Pasted image 20240826234218.png]]

## **Example**
```js
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ajax with PHP Example</title>
</head>
<body>
<h1>Ajax with PHP Example</h1>
<button id="fetchDataBtn">Fetch Data</button>
<div id="result"></div>
<script>
document.getElementById('fetchDataBtn').addEventListener('click', function() {
// Create an XMLHttpRequest object
var xhr = new XMLHttpRequest();
// Define what happens when the request is successful
xhr.onload = function() {
if (xhr.status === 200) {
// Update the result div with the response from the server
document.getElementById('result').innerHTML = xhr.responseText;
} else {
console.error('Error fetching data: ' + xhr.status);
}
};
// Define what happens in case of an error
xhr.onerror = function() {
console.error('Request failed');
};
// Open a connection to the PHP script
xhr.open('GET', 'fetch_data.php', true);

// Send the request
xhr.send();
});
</script>
<p>After the script</p>
</body>
</html>
```

`fetch_data.php`
```php
<?php
require_once '__dbconnect.php';
$data = [
'name' => 'John Doe',
'email' => 'john.doe@example.com',
'age' => 30
];
// Return the data as JSON
echo json_encode($data);
?>
```


## Ajax XMLHttpRequest object
![[Ajax XMLHttpRequest object]]

## Real time communication approaches
### Long Polling
![[Long polling]]

### Web Sockets
![[WebSocket]]



