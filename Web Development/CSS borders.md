#css 

## Shorthand

Border shorthand takes three properties: width, style, and color.

### Syntax:

```css
select{
    border: width style color;
}
```

## Border Width
Specifies the width of the border. Sets the width of the border in pixels(px), or there are values like medium, thin, and thick to set the border width.

```css
        .solid1 {
            border-width: 5px; //applies 5px to top,right, bottom and left
            border-style: solid;
            border-color: red;
        }
```

`border-width` has 4 values: top, right, bottom, left
```css
p.one {  border-style: solid;  
  border-width: 5px 20px; /* 5px top and bottom, 20px on the sides */}  
  
p.two {  border-style: solid;  
  border-width: 20px 5px; /* 20px top and bottom, 5px on the sides */}  
  
p.three {  border-style: solid;  
  border-width: 25px 10px 4px 35px; /* 25px top, 10px right, 4px bottom and 35px left */}
```

## border style

The `border-style` property specifies what kind of border to display.
The following values are allowed:

- `dotted` - Defines a dotted border
- `dashed` - Defines a dashed border
- `solid` - Defines a solid border
- `double` - Defines a double border
- `groove` - Defines a 3D grooved border. The effect depends on the border-color value
- `ridge` - Defines a 3D ridged border. The effect depends on the border-color value
- `inset` - Defines a 3D inset border. The effect depends on the border-color value
- `outset` - Defines a 3D outset border. The effect depends on the border-color value
- `none` - Defines no border
- `hidden` - Defines a hidden border

The `border-style` property can have from one to four values (for the top border, right border, bottom border, and the left border).

## Border Color

The border color property sets the colour of the border.

```CSS
.container{
	border-style:solid;
	border-color:red;
}
```
## Border on individual side
Example:
```css
p {  border-top-style: dotted;  
  border-right-style: solid;  
  border-bottom-style: dotted;  
  border-left-style: solid;}
```

## Border Radius
Used to add rounder borders:

```css
p {  border: 2px solid red;  
  border-radius: 5px;}
```