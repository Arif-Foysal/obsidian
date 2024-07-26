#javascript 

- [ ] Learn details later

By default, JavaScript will use the browser's time zone and display a date as a full text string:

**Fri Jul 26 2024 17:21:16 GMT+0600 (Bangladesh Standard Time)**

**9 ways to create a new date object:**
```js
new Date()  
new Date(date string)  
  
new Date(year,month)  
new Date(year,month,day)  
new Date(year,month,day,hours)  
new Date(year,month,day,hours,minutes)  
new Date(year,month,day,hours,minutes,seconds)  
new Date(year,month,day,hours,minutes,seconds,ms)  
  
new Date(milliseconds)
```
### `new Date()` 
`new Date()` creates a date object with the **current date and time**:
```Js
const d = new Date();
alert(d);
```
Output:
```
Fri Jul 26 2024 17:34:23 GMT+0600 (Bangladesh Standard Time)
```
