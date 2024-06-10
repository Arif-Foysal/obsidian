#html 

HTML elements are generally divided into two categories: **Block-level** and **Inline** elements.

### **Block Elements**
Elements that starts on a new line. No matter what the width is, block elements will start on a new line.
![[Pasted image 20240608175340.png]]

#### **Characteristics of Block Elements**
- Always start on a new line.
- Take up the full width available.
- Width and height can be controlled via CSS.
- Can contain other block-level as well as inline elements.
#### **Common Block Elements**
- `<h1>,<h2>,<h3>,<h4>,<h5>,<h6>` - Headings
- `<p>` - Paragraphs
- `<hr>` - Horizontal rule
- `<address>` - Address information
- `<article>` - Article content
- `<aside>` - Sidebar content
- `<blockquote>` - Block quotations
- `<canvas>` - Drawing area
- `<dd>` - Description in a description list
- `<div>` - Generic container
- `<dl>` - Description list
- `<dt>` - Term in a description list
- `<fieldset>` - Group of related form elements
- `<figcaption>` - Caption for a figure
- `<figure>` - Image or media with a caption
- `<footer>` - Footer of a section or page
- `<form>` - HTML form
- `<header>` - Header of a section or page
- `<li>` - List item
- `<main>` - Main content of a document
- `<nav>` - Navigation links
- `<noscript>` - Alternate content when JavaScript is not enabled
- `<ol>` - Ordered list
- `<ul>` - Unordered list
- `<pre>` - Preformatted text
- `<section>` - Standalone section in a document
- `<table>` - Table
- `<video>` - Video content
### **Inline Elements**
Inline elements are elements that do not start on a new line. It only takes the width required to cover the content.
### **Nesting Block and Inline Elements**
Inline elements can contain other inline elements, but they generally should not contain block-level elements.
For example, you could nest a `<strong>` (strong emphasis) element within a `<span>` (a generic inline container) element, like so:
```html
<span>This is <strong>important</strong> text.</span>
```

However, placing a block-level element like a `<div>` or `<p>` inside an inline element like `<span>` or `<a>` is typically considered incorrect HTML and could lead to unexpected behavior in terms of layout and styling. For example:
```html
<!-- This is generally considered incorrect -->
<span>This is <div>not recommended</div> text.</span>
```

### **Common Inline Elements**
- `<span>`: A generic inline container for text
- `<a>`: Defines a hyperlink
- `<strong>`: Defines important text
- `<em>`: Defines emphasized text
- `<img>`: Embeds an image
- `<input>`: Defines an input control


Here is an exhaustive list of the most used **Inline Elements:**
- `<a>`
- `<abbr>`
- `<acronym>`
- `<button>`
- `<br>`
- `<big>`
- `<bdo>`
- `<b>`
- `<cite>`
- `<code>`
- `<dfn>`
- `<i>`
- `<em>`
- `<img>`
- `<input>`
- `<kbd>`
- `<label>`
- `<map>`
- `<object>`
- `<output>`
- `<tt>`
- `<time>`
- `<samp>`
- `<script>`
- `<select>`
- `<small>`
- `<span>`
- `<strong>`
- `<sub>`
- `<sup>`
- `<textarea>`

**Ref:** https://www.codewithharry.com/tutorial/html-inline-elements/
