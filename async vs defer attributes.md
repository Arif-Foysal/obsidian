#javascript #webDevelopment 

## **Legend**
![[Pasted image 20240618145041.png]]
## `<script>`

Let’s start by defining what `<script>` without any attributes does. The HTML file will be parsed until the script file is hit, at that point parsing html file will stop and a request will be made to fetch the script file (if it’s external). The script will then be executed before parsing is resumed.
![[Pasted image 20240618145229.png]]
## `<script async>`
`async` downloads the file during HTML parsing and will pause the HTML parser to execute it when it has finished downloading.
![[Pasted image 20240618145605.png]]
## `<script defer>`
`defer` downloads the file during HTML parsing and will only execute it after the parser has completed. `defer` scripts are also guaranteed to execute in the order that they appear in the document.
![[Pasted image 20240618145659.png]]

## **When should I use what?**
Typically you want to use `async` where possible, then `defer` then no attribute. Here are some general rules to follow:

- If the script is modular and does not rely on any scripts then use `async`.
  **Example:** If the script performs tasks that don't require waiting for other scripts or the DOM to fully load.
- If the script relies upon or is relied upon by another script then use `defer`.
- If the script is small and is relied upon by an `async` script then use an inline `script` with no attributes placed _above_ the `async` scripts.







**Ref:**
https://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html