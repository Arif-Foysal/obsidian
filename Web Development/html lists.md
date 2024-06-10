#html #webDevelopment 

>[!Note]
>A list item (`<li>`) can contain a new list, and other HTML elements, like images and links, etc.
### **Unordered Lists**
```html
<ul>  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ul>
```
**Output:**
<ul>  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ul>

#### **Choose List Item Marker in ul**
The [[CSS]] `list-style-type` property is used to define the style of the list item marker. It can have one of the following values:

| Value  | Description                                     |
| ------ | ----------------------------------------------- |
| disc   | Sets the list item marker to a bullet (default) |
| circle | Sets the list item marker to a circle           |
| square | Sets the list item marker to a square           |
| none   | The list items will not be marked               |
**Example:**
```html
<ul style="list-style-type:disc;">  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ul>
```


#### **Horizontal Lists**
https://www.w3schools.com/html/html_lists_unordered.asp

### **Ordered Lists**
```
<ol>  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ol>
```
**Output:**
<ol>  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ol>

The `type` attribute of the `<ol>` tag, defines the type of the list item marker:

| Type     | Description                                                  |
| -------- | ------------------------------------------------------------ |
| type="1" | The list items will be numbered with numbers (default)       |
| type="A" | The list items will be numbered with uppercase letters       |
| type="a" | The list items will be numbered with lowercase letters       |
| type="I" | The list items will be numbered with uppercase roman numbers |
| type="i" | The list items will be numbered with lowercase roman numbers |
**Example:**
```html
<ol type="1">  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ol>
```

#### **Control the list counting**

By default, an ordered list will start counting from 1. If you want to start counting from a specified number, you can use the `start` attribute:
```html
<ol start="50">  
  <li>Coffee</li>  
  <li>Tea</li>  
  <li>Milk</li>  
</ol>
```

### **Description Lists**

```html
<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>
```

**Output:**
<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>

