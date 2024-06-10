#html 

A simple HTML table:
```html
<table>  
<caption>Company details</caption>
  <tr>  
    <th>Company</th>  
    <th>Contact</th>  
    <th>Country</th>  
  </tr>  
  <tr>  
    <td>Alfreds Futterkiste</td>  
    <td>Maria Anders</td>  
    <td>Germany</td>  
  </tr>  
  <tr>  
    <td>Centro comercial Moctezuma</td>  
    <td>Francisco Chang</td>  
    <td>Mexico</td>  
  </tr>  
</table>
```
**Output:**
<table>  
<caption><strong>Company details</strong></caption>
  <tr>  
    <th>Company</th>  
    <th>Contact</th>  
    <th>Country</th>  
  </tr>  
  <tr>  
    <td>Alfreds Futterkiste</td>  
    <td>Maria Anders</td>  
    <td>Germany</td>  
  </tr>  
  <tr>  
    <td>Centro comercial Moctezuma</td>  
    <td>Francisco Chang</td>  
    <td>Mexico</td>  
  </tr>  
</table>

- `<caption>` defines table caption
- Each table row starts with `<tr>`
- Table data starts with `<td>`
- Table head starts with `<th>`


### **colgroup tag**
The `<colgroup>` tag specifies a group of one or more columns in a table for formatting.

The `<colgroup>` tag is useful for applying styles to entire columns, instead of repeating the styles for each cell, for each row.

**Note:** The `<colgroup>` tag must be a child of a `<table>` element, after any `<caption>` elements and before any `<thead>`, `<tbody>`, `<tfoot>`, and `<tr>` elements.

```html
<table>  
  <colgroup>  
    <col span="2" style="background-color:red">  
    <col style="background-color:yellow">  
  </colgroup>  
  <tr>  
    <th>ISBN</th>  
    <th>Title</th>  
    <th>Price</th>  
  </tr>  
  <tr>  
    <td>3476896</td>  
    <td>My first HTML</td>  
    <td>$53</td>  
  </tr>  
</table>
```
**Output:**
![[Pasted image 20240607094522.png]]

### **Table Borders**
HTML tables can have borders of different styles and shapes.
To add a border, use the CSS `border` property on `table`, `th`, and `td` elements:
```css
table, th, td {  border: 1px solid black;}
```
**Output:**
![[Pasted image 20240607094830.png]]
To avoid having double borders, set the CSS `border-collapse` property to `collapse`.
```css
table, th, td {  border: 1px solid black;  
  border-collapse: collapse;}
```
**Output:**
![[Pasted image 20240607175109.png]]


## HTML Table Tags

HTML Table Tags
Tag 	Description
`<table>` 	Defines a table
`<th>` 	Defines a header cell in a table
`<tr>` 	Defines a row in a table
`<td>` 	Defines a cell in a table
`<caption>` 	Defines a table caption
`<colgroup>` 	Specifies a group of one or more columns in a                table for formatting
`<col>` 	Specifies column properties for each column within a         `<colgroup>` element
`<thead>` 	Groups the header content in a table
`<tbody>` 	Groups the body content in a table
`<tfoot>` 	Groups the footer content in a table

**Learn More:** https://www.w3schools.com/html/html_table_borders.asp

### **Table Size**
HTML tables can have different sizes for each column, row or the entire table.
https://www.w3schools.com/html/html_table_sizes.asp

### **Table Colspan and Rowspan**
To make a cell span over multiple columns, use the `colspan` attribute:
```html
<table>  
  <tr>  
    <th colspan="2">Name</th>  
    <th>Age</th>  
  </tr>  
  <tr>  
    <td>Jill</td>  
    <td>Smith</td>  
    <td>43</td>  
  </tr>  
  <tr>  
    <td>Eve</td>  
    <td>Jackson</td>  
    <td>57</td>  
  </tr>  
</table>
```

![[Pasted image 20240607184949.png]]

To make a cell span over multiple rows, use the `colspan` attribute:
```html
<table>  
  <tr>  
    <th>Name</th>  
    <td>Jill</td>  
  </tr>  
  <tr>  
    <th rowspan="2">Phone</th>  
    <td>555-1234</td>  
  </tr>  
  <tr>  
    <td>555-8745</td>  
</tr>  
</table>
```

![[Pasted image 20240607185102.png]]

### **Table Styling**
You can use CSS to make your table look good.
#### **Zebra Stripes**

- **Horizontal Zebra Stripes**
	```html
	<!DOCTYPE html>
	<html>
	<head>
	<style>
	table {
	  border-collapse: collapse;
	  width: 100%;
	}
	
	th, td {
	  text-align: left;
	  padding: 8px;
	}
	
	tr:nth-child(even) {
	  background-color: #D6EEEE;
	}
	</style>
	</head>
	<body>
	
	<h2>Zebra Striped Table</h2>
	<p>For zebra-striped tables, use the nth-child() selector and add a background-color to all even (or odd) table rows:</p>
	
	<table>
	  <tr>
	  <th>First Name</th>
	  <th>Last Name</th>
	  <th>Points</th>
	  </tr>
	  <tr>
	  <td>Peter</td>
	  <td>Griffin</td>
	  <td>$100</td>
	  </tr>
	  <tr>
	  <td>Lois</td>
	  <td>Griffin</td>
	  <td>$150</td>
	  </tr>
	  <tr>
	  <td>Joe</td>
	  <td>Swanson</td>
	  <td>$300</td>
	  </tr>
	  <tr>
	  <td>Cleveland</td>
	  <td>Brown</td>
	  <td>$250</td>
	  </tr>
	</table>
	
	</body>
	</html>
	```
	
	![[Pasted image 20240607185328.png]]
- **Vertical Zebra Stripes**
```html
<!DOCTYPE html>
<html>
<head>
<style>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

th:nth-child(even),td:nth-child(even) {
  background-color: #D6EEEE;
}
</style>
</head>
<body>

<h2>Striped Table</h2>
<p>For zebra-striped tables, use the nth-child() selector and add a background-color to all even (or odd) table rows:</p>

<table style="width:100%">
  <tr>
    <th>MON</th>
    <th>TUE</th>
    <th>WED</th>
    <th>THU</th>
    <th>FRI</th>
    <th>SAT</th>
    <th>SUN</th>
  </tr>
  <tr>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
  </tr>
  <tr>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
  </tr>
  <tr>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
  </tr>
  <tr>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
  </tr>
</table>

</body>
</html>
```

![[Pasted image 20240607185701.png]]

