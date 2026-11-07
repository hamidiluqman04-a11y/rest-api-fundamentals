# HTTP Fundamentals

## 1. What is HTTP?
**Hypertext Transfer Protocol (HTTP)** is a foundational communication protocol that enables clients and servers to exchange information across the web.
* **HTTP Request:** The structured message a client sends to a server.
* **HTTP Response:** The structured message a server returns to a client.

---

## 2. Anatomy of an HTTP Request
An HTTP request is composed of four essential parts:

### A. Method
Describes the explicit operation the client wants to perform on the resource:

| Method | Operational Meaning |
| :--- | :--- |
| **GET** | Retrieves data without changing state. |
| **POST** | Creates a brand new resource or triggers a specific processing operation. |
| **PUT** | Completely replaces an existing resource. |
| **PATCH** | Partially modifies or updates an existing resource. |
| **DELETE** | Removes a specific resource. |

### B. Path
The endpoint URL pattern representing the target resource.
* *Example:* `/products/10`

### C. Headers
Key-value pairs providing additional context and metadata about the request:

| Header | Meaning / Purpose |
| :--- | :--- |
| **Content-Type** | Dictates the data format being sent in the current request body. |
| **Authorization** | Contains credentials (e.g., API keys, Bearer tokens) used to authenticate the client. |
| **Accept** | Explicitly declares the response data formats the client is willing to receive. |

### D. Body
Contains the actual payload or raw data being transmitted to the server:
```json
{
    "name": "Gaming Mouse",
    "price": 120,
    "stock": 50
}
```

---

## 3. Anatomy of an HTTP Response
An HTTP response mirrors the request structure but returns data and execution statuses:

### A. Status
* **Status Code:** A three-digit numerical value representing the execution result of the request.
* **Status Message:** A short, human-readable text description explaining the status code.

### B. Headers
Key-value metadata sent back by the server providing context on the response:

| Header | Meaning / Purpose |
| :--- | :--- |
| **Content-Type** | Dictates the exact format of the returned response body data (e.g., `application/json`). |
| **Server** | Details the specific web server software utilized to generate the response. |

### C. Body
Contains the payload or actual dataset returned by the server:
```json
{
    "name": "Gaming Mouse",
    "price": 120,
    "stock": 50
}
```

---

## 4. Key Protocol Comparisons

### Content-Type vs. Accept
* **Content-Type:** Describes the data format you are **sending** in the request body.
* **Accept:** Describes the data format you are **willing to receive** back in the response body.

### Path Parameters vs. Query Parameters
* **Path Parameters:** Embedded variables inside the URL path used to **identify a specific resource**.
  * *Example:* `GET /products/10` *(Targeting product ID 10)*
* **Query Parameters:** Key-value extensions appended after the `?` character used to **filter, sort, search, or paginate** the request results without identifying a single resource.
  * *Example:* `GET /products?category=electronics&limit=10`

### PUT vs. PATCH
* **PUT:** Represents a complete resource **replacement**. The entire payload is swapped out.
* **PATCH:** Represents a **partial modification**. Only specified attributes are changed.

---

## 5. HTTP Status Code Categories
Status codes are divided into clear functional ranges that communicate the outcome:

### 2xx: Success
The request was successfully received, understood, and accepted.
* **200 OK:** The standard request was executed successfully.
* **201 Created:** The request succeeded and resulted in a new resource being made.
* **202 Accepted:** The request has been accepted for processing but is not yet complete.
* **204 No Content:** The request was successful, but there is no body payload to return.

### 3xx: Redirection
Further action needs to be taken by the client user agent to complete the request.
* **301 Moved Permanently:** The target resource has been assigned a brand new permanent URI.
* **302 Found:** The target resource resides temporarily under a completely different URI.
* **304 Not Modified:** The resource has not changed since the last request; the client can use its cached version.

### 4xx: Client Errors
The request contains bad syntax or cannot be fulfilled due to a client-side fault.
* **400 Bad Request:** The server cannot process the request due to perceived client errors (e.g., malformed syntax).
* **401 Unauthorized:** The request lacks valid authentication credentials.
* **403 Forbidden:** The server understands the request, but the client does not have access permissions.
* **404 Not Found:** The server cannot locate the requested resource endpoint.
* **409 Conflict:** The request could not be completed due to a data state conflict on the server.
* **422 Unprocessable Content:** The request is well-formed, but semantic errors prevent processing.
* **429 Too Many Requests:** The user has sent too many requests in a given amount of time (rate limiting).

### 5xx: Server Errors
The server failed to fulfill an otherwise completely valid request.
* **500 Internal Server Error:** A generic error message indicating an unexpected server condition.
* **502 Bad Gateway:** The server acting as a gateway received an invalid response from an upstream server.
* **503 Service Unavailable:** The server cannot handle the request because it is down for maintenance or overloaded.
* **504 Gateway Timeout:** The gateway server did not receive a timely response from the upstream server.
