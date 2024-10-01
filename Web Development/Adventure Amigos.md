#project #webDevelopment #SAD #dbms #root 

>[!Links]
>[[exchange rate api]]
>[[AI prompts for adventure amigos]]
>[[adventure amigos 1st presentation]]

# Tasks #todo 

## Front End

Goal is to finish the Front-End by [[2024-08-15]] 
- [ ] Reservation calendar
      https://preline.co/docs/datepicker.html
      or, flowbite
- [ ] Design the secondary nav.
- [ ] Finish create listings.
      -[x] make create_listing.php responsive
- [ ] Fix the nav bar responsive issue.
- [ ] Fix the profile menu and hamburger menu not working sometimes. #bug
- [ ] Use compilation of css instead of tailwind cdn.
- [x] Design activities page
[[2024-08-18]] finished the bottom tasks.3 left. adding more.....
- [x] View all review page

- [x] Fix tablet width of the language modal.
- [x] Edit profile.
- [x] Account settings -  
- [x] Account settings sub-pages.
      personal info, login and security, notifications, privacy and sharing, global preferences
- [x] view-hotel > all photos.
- [x] square images for hotels.php.


## Back End
- [ ] Use cookie for storing info (favorites, check-in details)
- [ ] Resize uploaded images before storing using [[intervension image]] library
- [ ] Handle currency and translate/ libretranslate api responses with guzzle http 
- [ ] Set chat application default conversation.
- [ ] Add profile visit and send message option.
#### Security
- [ ] sanitize and validate all external input
      [[PHP Filters]]
- [ ] 



# **Benchmark Analysis**

Existing websites to compare with:
https://beautifulbangladesh.gov.bd/

### **Prototype**
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fdesign%2FKGzx83c3lLMr3NKVizOC0v%2FAdventure-Amigos%3Ft%3DO2VvXIqrm4XPcViD-1" allowfullscreen></iframe>

# **Sprint Planning**
**Project Name:** Adventure Avenue

## **Sprint Tasks:**

- ## **Working with APIs**
	- **What is an API?**: Learn about what an API is, the difference between REST and SOAP APIs, and the purpose of HTTP methods (GET, POST, PUT, DELETE).
	- **JSON and XML**: Understand data formats used in APIs, focusing on JSON (JavaScript Object Notation) as it’s widely used in modern APIs.
	- ### **Handling HTTP Requests in PHP**
		- **Superglobals (`$_GET`, `$_POST`, `$_REQUEST`)**: Learn how to handle incoming HTTP requests.
		- **`file_get_contents` and `cURL`**: Practice sending HTTP requests from PHP using these methods to external APIs.
	- ### **Building a Simple API with PHP**
		- **Routing**: Set up basic routing using PHP to handle different API endpoints.
		- **Creating JSON Responses**: Learn how to return JSON data from your API using `json_encode()`.
		- **Handling HTTP Methods (GET, POST, PUT, DELETE)**: Learn how to detect and handle different request types using PHP's `$_SERVER['REQUEST_METHOD']`.
	- ### **Validating and sanitising data**
		- Validate and sanitise api inputs , or any kind of **external inputs**.
	- ### **Optional: API Authentication**
		- secure your API with authentication mechanisms like API keys, tokens, and OAuth.
	- ### **Fetching API data**
		- **POST Requests in Fetch API**: Learn how to send data from the frontend (JavaScript) to the backend (PHP) using POST requests.
		- Use [[Ajax]] to handle API data without refreshing the whole page.
