#ajax #javascript 

**Long polling** is a technique used to achieve **near real-time** communication between a client (like a web browser) and a server without the need for [[WebSocket]].

The client **repeatedly requests** information from the server, but with a key difference: instead of responding immediately, the server holds the request open until new data is available or a timeout occurs. Once the server sends the response, the client immediately sends a new request.
**Long Polling Workflow:**
- **Client Request**: The client sends an HTTP request to the server asking for updates.
- **Server Waits**: The server doesn’t respond immediately. Instead, it waits until there’s new data to send back or until a timeout occurs.
- **Server Response**: Once there’s new data (e.g., a new chat message), the server sends it back to the client.
- **Client Immediately Requests Again**: The client processes the data and immediately sends another request to the server to wait for more updates.

