It is a globally distributed network of servers that work together to deliver content efficiently
## Problems without CDN

- High latency due to geographic distance
- Overloaded origin servers
- Bandwidth constraints & slow load times
## CDN Architecture Overview

- Components of a CDN 
	- Origin Servers: Store the original content
	- Edge Servers (PoPs):  Store cached content closer to the users
	- Request Routing System: Directs users to the nearest PoP

## How does a CDN Works and Handles a User Request

1. User requests content
2. CDN directs the request to the nearest edge server
3. Cache Hit: If the content is available on the edge server, it is delivered instantly
4. Cache Miss: If the content is not cached, the request is forwarded to the origin server, and stored at the edge server for future use
## CDN Features

- Caching & Replication
- Load Balancing and request routing
- Compression & Optimization
- Security Features
## Use Cases of CDNs

- Static vs Dynamic Content Delivery
- API Acceleration & Edge Computing (CDNs for APIs)

