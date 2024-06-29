#PHP #superglobal #cookie

<iframe width="560" height="315" src="https://www.youtube.com/embed/SbAfPJj0H4g?si=WYAt878c0MjOsKn8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
### Cookie

Cookie is a small file that the server embeds on the user's computer. Each time the computer opens a webpage, the server will send a cookie to the computer. PHP contains  **setcookie** function to create a cookie object to be sent to the client along with HTTP response.

### Creating Cookies with PHP

A cookie can be created with the **setcookie()** function. 

**Syntax:**

```php
setcookie(name, value, expire, path, domain, secure, httponly);
```

#### Parameters

- Name − Name of the cookie stored.
- Value − This sets the value of the named variable.
- Expiry − This specifes a future time in seconds since 00:00:00 GMT on 1st Jan 1970.
- Path − Directories for which the cookie is valid.
- Domain − Specifies the domain name in very large domains.
- Security − 1 for HTTPS. Default 0 for regular HTTP.

- [ ] I'll learn it later when i'll need it. #todo 
