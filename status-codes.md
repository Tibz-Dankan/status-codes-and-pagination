The most commonly used HTTP status codes:

**1xx Informational**

- **100 Continue** - Server received request headers and client should proceed with request body
- **101 Switching Protocols** - Server is switching protocols as requested by client

**2xx Success**

- **200 OK** - Request succeeded, most common success response
- **201 Created** - Request succeeded and new resource was created
- **202 Accepted** - Request accepted for processing but not yet completed
- **204 No Content** - Request succeeded but no content to return

**3xx Redirection**

- **301 Moved Permanently** - Resource permanently moved to new URL
- **302 Found** - Resource temporarily moved to different URL
- **304 Not Modified** - Resource hasn't changed since last request, use cached version

**4xx Client Errors**

- **400 Bad Request** - Server can't process request due to client error (malformed syntax)
- **401 Unauthorized** - Authentication required to access resource
- **403 Forbidden** - Server understands request but refuses to authorize it
- **404 Not Found** - Requested resource doesn't exist on server
- **405 Method Not Allowed** - HTTP method not supported for this resource
- **429 Too Many Requests** - Client has sent too many requests in given time period

**5xx Server Errors**

- **500 Internal Server Error** - Generic server error, something went wrong
- **502 Bad Gateway** - Server acting as gateway received invalid response
- **503 Service Unavailable** - Server temporarily unavailable (maintenance/overload)
- **504 Gateway Timeout** - Server acting as gateway didn't receive timely response

These cover the vast majority of HTTP responses you'll encounter in web development and API interactions.
