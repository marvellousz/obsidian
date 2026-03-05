*TinyURL* is a URL shortening service that converts long URLs into short, unique links for easy sharing and tracking.

## Step 1
### Functional Requirements 

- Shorten a URL
- Redirect to Original URL
- Prevent duplicate short URLs
- User Authentication
### Non Functional Requirements

- High Availability
- Performance & Low Latency
- Scalability
- Reliability
### Unique URL Generation Strategies

- Random String Generation - collision
- UUID - long
- Hashing with Salt - long, collisions
- Base62 Encoding - recommended, can use some other method to avoid collisions
## Step 2

### Estimating Scale & Identifying Bottlenecks

- Estimated User Traffic
- Memory Requirement (Hot URL Cache)
- Network Bandwidth (Redirects)
- Storage Requirement (URL Mapping DB)
### Potential Bottlenecks

- High read volume - Focus on cache and fast DB reads
- Write throughput is moderate - Ensure consistency
- Latency sensitivity in redirects - Low latency infra needed
- Plan for burst traffic with autoscaling & CDN support
## Step 3

### API Design 

#### Create Short URL

- Accepts a long URL and returns a shortened URL
- Endpoint: POST /api/shorten
#### Redirect

- Redirect to Original URL
- Endpoint: GET /:short_key
	- eg: GET /abc123
- Behavior:
	- Looks up the original long URL using the short key
	- Returns a 302 HTTP Redirects to the long URL
#### Delete

- Endpoint: Delete /api/url/:short_key
- Behavior
	- Deletes the mapping if user is authenticated and owns the URL
	- Requires Bearer token for authentication
#### User Authentication APIs

- User Registration
- User Login
- Secure endpoint with bearer token
### High Level System Design

- API Gateway
- URL Shortener
- Redirect Service
- Database
- Cache Layer
- Auth Service
## Collision Handling in Distributed URL Generation - Hello Zookeeper

Distributed coordination service created by *Apache* 

- Atomic ID generation
- Guarantees unique ID
- Uses znodes to store and manage counters
- Supports distributed locking to serialize ID generation
## Step 4 (Strategic Tech & Infra Decisions for TinyURL)

- Database:
	- SQL (eg: PostgresSQL with auto-increment IDs)
	- NoSQL (eg: Redis for caching, DynamoDB for scalability)
	- Cache: Redis or Memcached for high-speed lookup
- Scalability & Performance
	- Horizontal scaling for URL generation services
- High Availability
	- Load Balancer to distribute traffic across service instances
	- Replication in DB to avoid single points of failure
	- Failover-ready infra using cloud-managed DBs or services 

![[Pasted image 20250829150104.png]]

