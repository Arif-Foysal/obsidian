#PHP #superglobal 

`$_SERVER` is a [[PHP Superglobals]] variable which holds the data about the headers, script locations, network addresses, paths, etc.

**Example**
```php
<?php
echo $_SERVER['PHP_SELF'] . '<br>';
echo $_SERVER['DOCUMENT_ROOT'] . '<br>';
echo $_SERVER['SERVER_ADDR'] . '<br>';
echo $_SERVER['SERVER_NAME'] . '<br>';
echo $_SERVER['REQUEST_METHOD'] . '<br>';
echo $_SERVER['REQUEST_TIME'] . '<br>';
echo $_SERVER['HTTP_USER_AGENT'] . '<br>';
echo $_SERVER['REMOTE_ADDR'];
?>
```

The following table lists some of the important elements of **$_SERVER**

| Element/Code                    | Description                                                                                |
| ------------------------------- | ------------------------------------------------------------------------------------------ |
| $_SERVER['PHP_SELF']            | Returns the filename of the currently executing script                                     |
| $_SERVER['GATEWAY_INTERFACE']   | Returns the version of the Common Gateway Interface the server is using                    |
| $_SERVER['SERVER_ADDR']         | Returns the IP address of the host server                                                  |
| $_SERVER['SERVER_NAME']         | Returns the name of the host server                                                        |
| $_SERVER['SERVER_SOFTWARE']     | Returns the server identification string                                                   |
| $_SERVER['SERVER_PROTOCOL']     | Returns the name and revision of the information protocol                                  |
| $_SERVER['REQUEST_METHOD']      | Returns the request method used to access the page                                         |
| $_SERVER['REQUEST_TIME']        | Returns the timestamp of the start of the request                                          |
| $_SERVER['QUERY_STRING']        | Returns the query string if the page is accessed via a query string                        |
| $_SERVER['HTTP_ACCEPT']         | Returns the Accept header from the current request                                         |
| $_SERVER['HTTP_ACCEPT_CHARSET'] | Returns the Accept_Charset header from the current reques                                  |
| $_SERVER['HTTP_HOST']           | Returns the Host header from the current request                                           |
| $_SERVER['HTTP_REFERER']        | Returns the complete URL of the current page                                               |
| $_SERVER['HTTPS']               | Is the script queried through a secure HTTP protocol                                       |
| $_SERVER['REMOTE_ADDR']         | Returns the IP address from where the user is viewing the current page                     |
| $_SERVER['REMOTE_HOST']         | Returns the Hostname from where the user is viewing the current page                       |
| $_SERVER['REMOTE_PORT']         | Returns the port being used on the user's machine to communicate with the web server       |
| $_SERVER['SCRIPT_FILENAME']     | Returns the absolute pathname of the currently executing script                            |
| $_SERVER['SERVER_ADMIN']        | Returns the value given to the SERVER_ADMIN directive in the web server configuration file |
| $_SERVER['SERVER_PORT']         | Returns the port on the server machine being used by the web server for communication      |
| $_SERVER['SERVER_SIGNATURE']    | Returns the server version and virtual host name which are added to server-generated pages |
| $_SERVER['PATH_TRANSLATED']     | Returns the file system-based path to the current script                                   |
| $_SERVER['SCRIPT_NAME']         | Returns the path of the current script                                                     |
| $_SERVER['SCRIPT_URI']          | Returns the URI of the current page                                                        |