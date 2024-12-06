# Web and API Concepts

## 1. API (Application Programming Interface)
- **Definition**: A set of rules and protocols for building and interacting with software applications.
- **Purpose**: Allows one application to communicate with another (e.g., a frontend interacting with a backend).
- **Examples**: REST API, GraphQL, gRPC.

---

## 2. Local Storage
- **Definition**: A client-side storage mechanism provided by web browsers.
- **Purpose**: Stores data persistently (even after the browser is closed) in key-value pairs.
- **Characteristics**:
  - Capacity: Up to 5-10 MB depending on the browser.
  - Example Use Case: Saving user preferences or session tokens.

---

## 3. REST API (Representational State Transfer API)
- **Definition**: A widely used architectural style for designing networked applications.
- **Key Principles**:
  - **Stateless**: Each request from a client must contain all information for the server to process it.
  - **Endpoints**: Defined URLs represent resources (e.g., `/users` or `/products`).
  - **HTTP Methods**:
    - `GET`: Read data.
    - `POST`: Create data.
    - `PUT`/`PATCH`: Update data.
    - `DELETE`: Remove data.

---

## 4. Pagination
- **Definition**: A technique for dividing large sets of data into smaller, manageable chunks.
- **Purpose**: Improves performance and user experience by retrieving data in portions.
- **Common Approaches**:
  - **Offset-Based**: `?page=2&limit=10`.
  - **Cursor-Based**: Uses a unique identifier as a pointer for the next page.

---

## 5. Session
- **Definition**: A server-side mechanism to maintain state and track users during their interactions with a website.
- **Purpose**: Stores user-specific information (e.g., login status) temporarily.
- **Implementation**: Often uses a session ID stored in cookies or sent in HTTP headers.

---

## 6. Cookies
- **Definition**: Small text files stored on the client side by a website.
- **Purpose**:
  - Store user data like preferences or session tokens.
  - Enable persistent state between requests.
- **Types**:
  - **Session Cookies**: Deleted when the browser is closed.
  - **Persistent Cookies**: Remain until they expire or are deleted.

---

## 7. JSON (JavaScript Object Notation)
- **Definition**: A lightweight data-interchange format.
- **Characteristics**:
  - Human-readable.
  - Consists of key-value pairs.
- **Example**:
  ```json
  {
    "name": "John",
    "age": 30,
    "isStudent": false
  }
```
## 8. GraphQL
- **Definition**: A query language for APIs and a runtime for executing those queries against your data.
- **Purpose**: Provides a flexible and efficient alternative to REST APIs by allowing clients to request exactly the data they need.

### Key Features:
1. **Single Query**:
   - Clients can fetch data from multiple resources in a single request.
   - Example:
     ```graphql
     query {
       user(id: 1) {
         name
         email
         posts {
           title
           content
         }
       }
     }
2. **Mutations**:
   - Used to modify data on the server (e.g., create, update, delete).
   - Example:
     ```graphql
     mutation {
       createPost(title: "GraphQL Basics", content: "Introduction to GraphQL") {
         id
         title
         content
       }
     }
     ```
3. **Subscriptions**:
   - Supports real-time updates through WebSocket connections.
4. **Schema**:
   - Strongly typed schema defines the API's structure, including types, queries, and mutations.

### Advantages:
- Fetch only the required data, reducing over-fetching or under-fetching.
- Self-documenting: Clients can explore the API schema interactively.
- Supports nested and complex queries.

### Built on HTTP POST:
- Queries and mutations are typically sent as POST requests with a JSON payload to a single endpoint, such as `/graphql`.

---

## 9. gRPC (Google Remote Procedure Call)
- **Definition**: A high-performance, open-source framework developed by Google for enabling communication between distributed systems using Remote Procedure Calls (RPC).
- **Purpose**: Allows a client to directly call methods on a server as if it were a local object.

### Key Features:
1. **Protocol Buffers (Protobuf)**:
   - A language-neutral, efficient serialization format used for defining the structure of requests and responses.
   - Example `.proto` file:
     ```proto
     syntax = "proto3";

     service UserService {
       rpc GetUser (GetUserRequest) returns (GetUserResponse);
     }

     message GetUserRequest {
       int32 id = 1;
     }

     message GetUserResponse {
       string name = 1;
       string email = 2;
     }
     ```
2. **Multi-language Support**:
   - Works with multiple programming languages, including Python, Go, Java, and C++.
3. **HTTP/2**:
   - Provides features like multiplexing and low latency.
4. **Streaming**:
   - Supports client-side, server-side, and bidirectional streaming.

### Comparison to REST:
| Feature        | REST                     | gRPC                        |
|----------------|--------------------------|-----------------------------|
| Serialization  | JSON                     | Protocol Buffers (Protobuf) |
| Performance    | Slower                   | Faster                      |
| Streaming      | Limited                  | Full bi-directional support |
| Schema         | Not enforced (optional)  | Strictly defined schema     |
| Transport      | HTTP/1.1 or HTTP/2       | HTTP/2                      |

### Advantages:
- Faster due to binary serialization.
- Strongly typed API with Protobuf schemas.
- Bi-directional streaming for real-time use cases.

### Use Cases:
- Microservices communication.
- Real-time systems like IoT, chat apps, and live data feeds.
