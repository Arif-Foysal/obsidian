#css 

![[css-margin-padding.png]]
The CSS `margin` properties are used to create space around elements, outside of any defined borders.

**Syntax**:
```css
selector{
    margin: top right bottom left;
}
```

## Margin on individual sides
- `margin-top`
- `margin-right`
- `margin-bottom`
- `margin-left`

```css
p {  margin-top: 100px;  
  margin-bottom: 100px;  
  margin-right: 150px;  
  margin-left: 80px;}
```

All the margin properties can have the following values:
- auto - the browser calculates the margin
- _length_ - specifies a margin in px, pt, cm, etc.
- _%_ - specifies a margin in % of the width of the containing element
- inherit - specifies that the margin should be inherited from the parent element
- [ ] Clear understanding about auto #todo 

## Margin Collapse
Top and bottom margins of elements are sometimes collapsed into a single margin that is equal to the largest of the two margins.

```css
h1 {  margin: 0 0 50px 0;}  
  
h2 {  margin: 20px 0 0 0;}
```
In the example above, the `<h1>` element has a bottom margin of 50px and the `<h2>` element has a top margin set to 20px.

Common sense would seem to suggest that the vertical margin between the `<h1>` and the `<h2>` would be a total of 70px (50px + 20px). But due to margin collapse, the actual margin ends up being 50px.

