## What is API Design?
- **Definition**: The process of defining the structure, endpoints, and behavior of an API to ensure it is easy to use, scalable, and maintainable.
- **Goal**: To create a clear, consistent, and efficient interface that meets the needs of both developers and users.

---

## Key Principles of API Design

### 1. **Consistency**
- Use predictable patterns across endpoints, naming conventions, and behaviors.
- Example:
  - Endpoints for user data:
    - `GET /users` – Fetch all users.
    - `GET /users/{id}` – Fetch a single user.
    - `POST /users` – Create a user.
    - `PUT /users/{id}` – Update a user.
    - `DELETE /users/{id}` – Delete a user.

---

### 2. **Versioning**
- Maintain backward compatibility and allow for iterative changes.
- Methods:
  - URL versioning: `/v1/users`
  - Header versioning: `Accept: application/vnd.example.v1+json`

---

### 3. **Use Proper HTTP Methods**
- Match the appropriate HTTP method with the action:
  - `GET`: Retrieve data.
  - `POST`: Create a new resource.
  - `PUT`: Update an existing resource (replace entirely).
  - `PATCH`: Update a part of a resource.
  - `DELETE`: Remove a resource.

---

### 4. **Use Clear and Descriptive Endpoints**
- Use nouns to represent resources, not verbs.
- Example:
  - **Good**: `/products`, `/users/{id}/orders`
  - **Bad**: `/getUser`, `/createOrder`

---

### 5. **Error Handling**
- Provide meaningful and consistent error messages.
- Use appropriate HTTP status codes:
  - `200 OK`: Success.
  - `201 Created`: Resource successfully created.
  - `400 Bad Request`: Client error (invalid input).
  - `401 Unauthorized`: Authentication required.
  - `404 Not Found`: Resource not found.
  - `500 Internal Server Error`: Server issue.

---

### 6. **Pagination**
- Implement pagination for large datasets to improve performance.
- Example:
  - Offset-based: `GET /users?page=2&limit=10`
  - Cursor-based: `GET /users?cursor=abc123`

---

### 7. **Data Formats**
- Use standardized formats like **JSON** or **XML** for data exchange.
- Default to JSON as it is widely supported and human-readable.

---

### 8. **Security**
- Use **HTTPS** to encrypt data in transit.
- Implement authentication and authorization:
  - **API Keys**: Basic access control.
  - **OAuth2**: For user-level permissions.
  - **JWT**: For stateless authentication.
- Validate and sanitize all inputs to prevent attacks like SQL injection or XSS.

---

### 9. **Documentation**
- Provide clear, detailed, and interactive documentation.
- Tools: Swagger (OpenAPI), Postman, or API Blueprint.
- Include:
  - Endpoint descriptions.
  - Request and response examples.
  - Authentication details.

---

## API Design Example: REST API

### Endpoints for a Blog Application:
```plaintext
GET    /posts            # Retrieve all posts
GET    /posts/{id}       # Retrieve a single post
POST   /posts            # Create a new post
PUT    /posts/{id}       # Update a post
DELETE /posts/{id}       # Delete a post
