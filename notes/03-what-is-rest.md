# 03 What is REST?

## 1. What is REST?
**Representational State Transfer (REST)** is an architectural style that provides strict guidelines for how the client and server should communicate and organize resources.

## 2. What is a Resource?
* A **resource** is any piece of data or information that the API makes accessible to the client.
* **HTTP Methods** (e.g., `GET`, `POST`, `PUT`, `DELETE`) explicitly describe the action or operation we want to perform on that specific resource.

## 3. The 6 REST Constraints
To be considered truly RESTful, an API must adhere to these foundational constraints:
1. **Client-Server Separation:** The frontend and backend hold distinct responsibilities and operate independently.
2. **Statelessness:** Every single request must contain all the information necessary for the server to process it; the server stores no session context about the client.
3. **Cacheability:** Responses must define themselves as cacheable or non-cacheable so clients can temporarily store and reuse data to improve performance.
4. **Uniform Interface:** The system enforces consistent naming conventions and standard HTTP semantics so the API is universally easy to understand.
5. **Layered System:** The client cannot necessarily tell whether it is connected directly to the end server or interacting via intermediaries (like load balancers or proxies).
6. **Code on Demand (Optional):** The server can temporarily extend client functionality by transferring executable code (e.g., JavaScript scripts).

## 4. RESTful vs. Non-RESTful Endpoint Design
RESTful design shifts the focus from actions (verbs in the URL) to resources (nouns in the URL), utilizing standard HTTP methods to dictate the action.

| Action | Non-RESTful Design (RPC Style) | RESTful Design |
| :--- | :--- | :--- |
| **Fetch All Products** | `GET /getAllProducts` | `GET /products` |
| **Create a Product** | `POST /createNewProduct` | `POST /products` |
| **Delete a Product** | `POST /deleteProduct/10` | `DELETE /products/10` |

### Core RESTful Design Rules:
* **URLs represent resources** (expressed as plural nouns).
* **HTTP methods describe operations** instead of embedding verbs in the URL path.
* **Consistent naming structures** are strictly maintained.
* **Standard HTTP semantics** are fully utilized.

## 5. E-Commerce REST API Endpoint Examples
Below are clean examples of RESTful endpoints organized around key e-commerce resources (Products, Customers, Orders, Payments, and Carts):

* **Products**
  * `GET /products` — Fetches the list of all available products.
  * `GET /products/1` — Fetches detailed information for a specific product (ID: 1).
* **Customers & Orders**
  * `GET /customers/1/orders` — Retrieves the entire order history for a specific customer.
  * `POST /customers/1/orders` — Places a brand new order on behalf of a specific customer.
* **Shopping Carts**
  * `DELETE /customers/1/cart` — Entirely clears or removes the shopping cart for a specific customer.
