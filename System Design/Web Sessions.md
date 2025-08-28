Web apps often need to track user state. HTTP is stateless, meaning each request is independent.
## Techniques

- Session Based Auth (Server-side session storage + Cookies for session IDs)
	- The server maintains session status
	- The client holds only a session ID
- Token Based Auth (JWTs, OAuth Tokens)
	- The session state is embedded within the token itself
	- The server does not need to track user sessions
## Security Concerns in Session Management

- Session Hijacking 
- Cross-Site Request Forgery
- Secure Cookie Handling
## Best Practices for Scaling Session Management

- Sticky Sessions vs Distributed Sessions
- Storing Session Data in Redis, Memcached
- Stateless authentication (JWTs) for scalability
