# 01 What is API

## 1. What is an API?
An **Application Programming Interface (API)** acts as the intermediary between the client side and the server. 
* **The Mechanism:** When a client sends a request (e.g., `GET /item`), the API routes this request to the server, retrieves the requested data, and delivers the response back to the client.

## 2. Why Do Applications Need APIs?
Applications rely on APIs to **enable seamless communication** between the client and the server, decoupling the user interface from the backend logic.

## 3. Client vs. Server
The core distinction lies in their roles during a network transaction:
* **Client:** The entity that initiates the interaction by **sending a request**.
* **Server:** The entity that processes the request and **returns the response**.

| Component | Primary Role | Example |
| :--- | :--- | :--- |
| **Client** | Sends requests | Web browser, Mobile app |
| **Server** | Sends responses | Cloud server, Backend application |

## 4. The Role of a Database
A database serves as the dedicated storage system that **persists and manages data** for an application.

## 5. Lifecycle of a Product Request
1. **Initiation:** The client sends a request to the API.
2. **Routing:** The API accepts the request and forwards it to the server.
3. **Processing:** The server processes the request and fetches the required data from the database.
4. **Data Delivery:** The server formats the retrieved data into a JSON response and passes it back to the API.
5. **Completion:** The API delivers the final JSON response back to the client.
