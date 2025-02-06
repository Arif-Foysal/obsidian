#REST #API 

A **RESTful API** (Representational State Transfer API) is a web service that follows [[REST principles]] to allow communication between clients and servers using standard HTTP methods.

- **Stateless** – Each request from a client to the server must contain all the information needed to process it. The server does not store client state between requests.
- **Client-Server Architecture** – The client and server are separate, allowing independent development and scaling.
- **Uniform Interface** – Resources are identified using URLs, and standard HTTP methods are used to perform operations.
- **Cacheable** – Responses can be cached to improve performance.
- **Layered System** – The API may have multiple layers (e.g., security, load balancing), but the client interacts as if it's a single system.
- **Uses JSON or XML** – Most REST APIs use **JSON** for data exchange due to its simplicity and readability.
