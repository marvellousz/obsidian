Problem: Browsers enforce Same-Origin Policy (SOP), blocking cross-origin requests by defaults.
## The Need for CORS

- Modern web apps rely on APIs hosted in different domains
- CORS is a mechanism that allows secure cross-origin communication
## How CORS work?

- CORS is server-driven - the server must explicitly allow access
- Two types of requests:
	- Simple Request: GET, POST (without custom headers)
	- Preflight requests: Needed for PUT, DELETE, or custom headers
- CORS Header Control:
	- Access-Control-Allow-Origin (which origins can access)
	- Access-Control-Allow-Methods (allowed HTTP methods)
	- Access-Control-Allow-Headers (custom headers that can be sent)
## Preflight Requests & CORS Headers

- Some requests require checks (sent via OPTIONS request)
- Browser first sends a preflight request before making the actual request
- If the server responds with valid CORS headers, the browser allows the actual request
- Key Headers:
	- Access-Control-Allow-Origin: https://example.com
	- Access-Control-Allow-Methods: GET, POST
	- Access-Control-Allow-Headers: Authorization, Content-Types
## Security Risks & Common Misconfiguration

- Overly permissive CROS
- Allowing creds with *
- Exposing sensitive APIs via improper CORS settings
## Strategies to fix it

- Use a whitelist of trusted origins instead of *
- Set correct CORS policies for different API endpoints
- Use Reverse Proxies or API Gateways to handle CORS securely
## Handling CORS in APIs

- CORS in REST APIs
	- JSON based APIs commonly use CORS
	- Configure headers properly in backend frameworks 
- CORS in GraphQL APIs
	- GraphQL APIs also need CORS handling since they operate over HTTP
	- Preflight requests occur due to complex queries & mutations
## Alternatives to CORS & Role of API Gateways

- Alternatives to CORS for Cross-Origin Requests
	- Reverse Proxy
		- Forwards client requests to the backend, bypassing browser CORS restrictions
		- Nginx proxying requests to the backend, bypassing browser CORS restrictions
	- API Gateway Handling CORS
		- Centralized control of CORS policies for multiple services
		- Example: AWS API Gateway configuring allowed origins
- How API Gateway & Reverse Proxies Help?
	- Reverse Proxies handle cross-origin requests internally to avoid CORS issues.
	- API Gateways enforce CORS policies centrally, ensuring security & consistency.
	- Both improve performance by reducing unnecessary browser preflight requests.