# 02 Client Server

**Scenario:** A customer wants to purchase two keyboards. 
* **Endpoint:** `POST /orders`
* **Payload:**
```json
{
  "product_id": 10,
  "quantity": 2
}
```

---

### 1. Which component initiates the request?
The **frontend (client)** initiates the request. It sends the `POST /orders` request alongside the JSON body to inform the server exactly what item and quantity the customer wants to buy.

### 2. Which component receives and processes it?
The **API / Backend Server** receives the incoming request, parses the data, and routes it to the specific controller or handler designed to process orders.

### 3. What information should the backend retrieve from the database?
The backend needs to fetch essential product details using the provided `product_id`. At a minimum, it retrieves:
* The **product name** (for receipt/order confirmation displays).
* The **current stock inventory level** (to check availability).
* The **product price** (to calculate the total cost).

### 4. What should the backend check before creating the order?
Before saving the order to the database, the backend must perform critical validation checks:
* **Stock Availability:** Ensure the available inventory quantity is greater than or equal to the requested quantity (`2`).
* **Product Existence:** Verify that a product with `product_id: 10` actually exists in the database.

### 5. After successfully creating the order, what should the backend return to the client?
The backend should return a clear response string or JSON status message depending on the outcome of the validations:

| Scenario | Response Message / Body | Status Code |
| :--- | :--- | :--- |
| **Success** | `"product created keyboard:2"` | `201 Created` |
| **Out of Stock** | `"product out of stock"` | `400 Bad Request` |
| **Product Missing** | `"product not found"` | `404 Not Found` |
