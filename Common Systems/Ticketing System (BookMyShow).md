## Step 1
### Functional Requirements

- Users should be able to 
	- Browse events and view seats
	- Book/Reserve
	- Get real time seat availability
	- Pay for tickets
	- Receive email/SMS confirmations
- Admins
	- Create/manage events and venues
	- Define seat layouts and pricing
### Non Functional Requirements

- High Availability
- Low Latency
- Scalability
- Data Consistency
- Audit Logs
### Constraints & Challenges

- 5M total users, 100K concurrency users at peak
- Global event organizers
-  Handling payment failures
## Step 2

### Estimating Scale & Identifying Bottlenecks

- User Load Assumptions
- Booking Traffic Estimations
### Identifying System Bottlenecks

- Concurrency in Seat Allocation]
- Database Write Pressure
- Payment and External API Latency
- Notification Backlogs
## Step 3
### Core Components

- Web & Mobile
- API Gateway
- Authentication
- Admin Portal
### Backend Services

- Event Management Service
- Seat Inventory Service
- Booking Service
- Payment Service
- Notification Service

![[Pasted image 20250830001015.png]]
### Data & Caching Architecture

- Relational DB
- NoSQL DB
- Caching Layer
- Queue System
### Notable Design Decisions

- Concurrency Control
- Seat Hold Timeout Logic
- CQRS Pattern
- Idempotency Keys for Payments
### API Design

- Event Management Service
- Booking Service
## Step 4

- API Gateway: NGINX, AWS API Gateway
- Auth: OAuth 2.0 with JWT tokens
- Booking DB: Choose PostgreSQL for strong consistency and transactional support
- Event & Venue Data: Use MongoDB or Elastisearch 
- Caching: Redis
- Async Messaging: Kafka
- Payment: Stripe, RazorPay
- Notifications: AWS SES for emails. Twilio for SMS
- Infrastructure: Kubernetes with auto scaling 
- Monitoring: Leverage Prometheus, Grafana
- Logging: Elastisearch, Kibana
## The Final Design

![[Pasted image 20250830001956.png]]

