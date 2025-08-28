It is a software design pattern that structures apps into multiple layers, each responsible for specific functions. The increases scalability, maintainability and security.

## Key Points

- Organizes apps into independent layers
- Separates concerns: UI, business logic and data storage
- Enables better scalability, performance and security
- Used in web apps, enterprise systems and cloud architectures
## 2-Tier Architecture

This architecture consists of a client layer and a database layer. The client interacts directly with the database, without an intermediate business logic layer.

### Pros

- Simple to implement
- Fast for small-scale apps
### Cons

- Poor scalability
- Security risks
## 3-Tier Architecture

It introduces a middle layer between the UI and the database.

### Pros

- Improves scalability & security
- Better separation of concerns
- Easier maintenance
### Cons

- Slightly higher latency due to extra processing
- Eg: Traditional web apps

## N-Tier Architecture

It extends beyond  3-Tier by adding more specialized layers like caching, API gateway, microservices.

### Why use N - Tier?

- Handles high-traffic & complex business logic 
- Allows independent scaling of different services

### Examples

- Microservices based apps
- Large scale enterprise software
## Performance & Scalability Impacts

- More layers means higher latency if not optimized (Solution: Caching (Redis, Memcached), Load Balancing)
- Vertical Scaling (adding resource to a single server)
- Horizontal Scaling (adding more servers, distributing load)