#html #webDevelopment 

**An image map is an image with clickable areas.**

Here is the HTML source code for the image map above:
```html
<img src="workplace.jpg" alt="Workplace" usemap="#workmap">  
  
<map name="workmap">  
  <area shape="rect" coords="34,44,270,350" alt="Computer" href="computer.htm">  
  <area shape="rect" coords="290,172,333,250" alt="Phone" href="phone.htm">  
  <area shape="circle" coords="337,300,44" alt="Coffee" href="coffee.htm">  
</map>
```

The idea behind an image map is that you should be able to perform different actions depending on where in the image you click.
#### **The attributes and tags used:**
- The `usemap` value starts with a hash tag `#` followed by the name of the image map, and is used to create a relationship between the image and the image map.
- The `name` attribute must have the same value as the `<img>`'s `usemap` attribute .
- A clickable area is defined using an `<area>` element.
- **Shape:**
	- `rect` - defines a rectangular region
		- The shape `rect` comes in pairs, one for the x-axis and one for the y-axis. 
		  So, the coordinates `34,44` is located 34 pixels from the left margin and 44 pixels from the top:
		  ![[Pasted image 20240605233627.png]]
		  The coordinates `270,350` is located 270 pixels from the left margin and 350 pixels from the top:
		  ![[Pasted image 20240605233657.png]]
		  
	- `circle` - defines a circular region
	- `poly` - defines a polygonal region
	- `default` - defines the entire region

GO to ref to learn more
**Ref**: https://www.w3schools.com/html/html_images_imagemap.asp