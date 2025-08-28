## Uses of LB

- High Availability
- Traffic Distribution
- Prevents Overload
- Improves Performance
- Handles Failures Gracefully
- Supports Scalability

## Types of Load Balancers

### Based on Layer

- Layer 4: Operates at TCP/UDP level, distributing requests based on network-level data
- Layer 7: Operates at HTTP/HTTPS level, making routing decisions based on request content

### Based on Deployment

- Hardware Load Balancers: Specialized devices (eg: F5, Citrix, NetScaler)
- Software Load Balancers:  Nginx, HAProxy, Envoy
- Cloud based Load Balancers: AWS Elastic Load Balancers, Google Cloud Load Balancing

## Load Balancing Strategies

### Static Loading Balancing

- Round Robin: Distributes requests sequentially to each server
- Least Connections: Directs traffic to the server with the fewest connections
- IP Hashing: Routes requests based on client IP
### Dynamic Load Balancing

- Least Response Time: Sends requests to the server with the fastest response
- Adaptive Load Balancing: Uses real-time monitoring to make decisions
- Weighted Load Balancing: Assigns different weights to servers based on capacity





