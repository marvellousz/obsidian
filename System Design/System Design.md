## History

**1995 - 2005**: Early Monolithic Web Applications

**2005 - 2010**: Scaling Challenges & Distributed Systems

**2010 - 2015**: The Cloud Revolution

**2015 - 2020**: Microservices & Event-Driven Architectures

**2020 - Present**: Real-Time, AI-Driven & Edge Computing

## Networking in System Design

1. Every system relies on data exchange between components.
2. Networking enables scalability, reliability, and performance.

## Concepts in System Design

### Networking and Communication

1. [[IP Address]]

2. [[DNS]]

3. [[Client - Server Model]]

4. [[Proxy]]

5. [[Load Balancers]]

6. [[API Gateway]]

7. [[CDN]]
## Protocols

1. [[TCP]]

2. [[UDP]]

3. [[HTTP]]

4. [[REST]]

5. [[Real-Time Communication]]

6. [[Modern API Protocols]]
## Architectural Patterns

- The structure of a system, including its components and relationships
- Architecture impacts scalability, performance, and maintainability
### Considerations

- Scalability
- Maintainability
- Performance

Keep in mind, the architectural choices you make directly influence system behavior

1. [[Software Architecture Patterns & Styles]]
2. [[Multi-Tier Architecture]]
3. [[Microservices Architecture]]
4. [[Event-Driven Architecture]]
## Web Concepts in System Design

1. [[Web Sessions]]
2. [[Serialization]]
3. [[CORS]]
## [[Scalability]] in System Design

It is the ability of a system to handle an increasing amount of work or its potential to accommodate growth.
## [[Load Balancers]]

### Why is Load Balancing is Needed?

- High Availability
- Traffic Distribution
- Prevents Overload
- Improves Performance
- Handles Failures
- Supports Scalability
- Example: A high-traffic e-commerce site uses load balancing to handle peak-hour requests
### Types of Load Balancers

#### Based on Layer

- Layer 4 (Transport Layer): Operates at TCP/UDP level, distributing requests based on network-level data
- Layer 7 (Application Layer): Operates at HTTP/HTTPS level, making routing decisions based on request content
#### Based on Deployment

- Hardware Load Balancers: Specialized devices (EG:F5, Citrix NetScaler)
- Software Load Balancers: Nginx, HAProxy, Envoy
- Cloud-based Load Balancers: AWS Elastic Load Balancer (ELB), Google Cloud Load Balancing
### Load Balancing Strategies
#### Static Load Balancing

- Round Robin
- Least Connections
- IP Hashing
#### Dynamic Load Balancing

- Least Response Time
- Adaptive Load Balancing
- Weighted Load Balancing
### Load Balancer in Action

- Example Scenario
	- A web app with multiple servers
	- Users send requests, and the load balancers distributes them efficiently
### Choosing the Right Load Balancer

- Layer 4 vs Layer 7
- Scalability Needs
- Security Concerns
- Use Cases:
	- Nginx/HAProxy for web apps
	- AWS ELB for cloud native apps
	- Hardware Load Balancers for enterprise data centers
## [[Autoscaling]]

- Automatic adjustment of compute resources based on load
- Ensures performance, availability, and cost-efficiency
- Common in microservices, web apps, and event-driven systems
## [[Database and Storage]]

### Why Storage Matters?

- All systems generate and consume data storing it is essential
- Storage impacts performance, reliability, cost
- Persistent storage enables everything from user profiles to search history to analytics
### [[CAP Theorem]]

*Consistency, Availability, Partition Tolerance* (only guarantee 2/3)
### What is a Database?

Something which can be used for storing and accessing data
### Intro to Relational DB

- Eg: MySQL, PostgreSQL, Oracle
- Data stored in rows and columns
- Enforces strict schema (structure)
- Uses SQL (Structured Query Language)
### Core Concepts of Relational Database

- Schemas: Predefined structure
- Joins: Combine data across multiple tables
- ACID Properties:
	- Atomicity - all or nothing
	- Consistency - data integrity maintained
	- Isolation - transactions don't interfere
	- Durability - change survive system failures 
### Limitations of Relational DB

- Not ideal for:
	- Rapidly changing or schema-less data
	- Large-scale horizontal scaling
	- Flexible or nested data (eg: JSON blobs)
### Intro to NoSQL

- Designed for flexibility and scale
- Schema-less or dynamic schema
- Types:
	- Document (MongoDB)
	- Key-Value (Redis, DynamoDB)
	- Columnar (Cassandra, HBase)
	- Graph (Neo4j)
### NoSQL - Deep Dive

- Document Databases
	- JSON-like structure (key-value pairs, nesting supported)
	- Ideal for content management, user profiles
	- Eg: MongoDB
- Key-Value Pairs
	- Simple, fast, key-based lookups
	- High performance, low latency
	- Example: Redis, DynamoDB
- Columnar Databases
	- Store data by column, not row
	- Optimized for analytical queries over large datasets
	- Example: Cassandra, HBase
- Graph Databases
	- Store entities and relationships as nodes and edges
	- Efficient for highly connected data (eg: social networks)
	- Example: Neo4j
### BASE Properties in NoSQL

- Basically Available: Always returns a response (even if stale)
- Soft state: System state may change over time
- Eventually consistent: Data will be consistent.... eventually 
### CAP Theorem 

- Consistency, Availability, Partition Tolerance
- No distributed system can guarantee all 3
- SQL tends towards CP, NoSQL systems often choose AP or BASE
### When to use what

#### When to use SQL

- Complex queries and relationships
- Strong consistency needed
- Structured and well-known schema
- Example: Banking, ERP, Inventory Systems
#### When to use NoSQL

- High scalability needed
- Flexibility or evolving data structure
- Low-latency or high-volume operations
- Example: IoT, Recommendation Systems, Caching, Logs
### Advanced Database Topics

Vertical Scaling (Scale-Up) - Traditional SQL Databases
Horizontal Scaling (Scale-Out) - Modern NoSQL Databases

### What is Replication?

Copying data from one database node to another for redundancy and performance
#### Benefits

- Fault Tolerance
- Read performance improvement
- Data availability
#### Trade-offs in real-world systems (CAP Theorem)

- Replication may favor availability
- Strong consistency may sacrifice availability
### Leader-Follower Replication

#### How it works?

- Writes go to the Leader
- Reads from Followers
#### Consistency Consideration

- Asynchronous Replication = possible lag
### Read Replicas

#### Use case:

- Scaling read-heavy workloads
#### Differences from Leader-Follower:

- Often used just for load balancing reads
- Dosen't take part in writes
### What is Sharding?

Splitting data across multiple databases to scale horizontally
#### Why it's needed?

- Performance and storage limits of a single node
### Types of sharding

- Horizontal Sharding: Rows are distributed across shards (most common)
- Vertical Sharding: Tables or columns are split across shards based on function or access pattern
### Sharding Techniques

##### Range-Based Sharding

- Split by value ranges 
- Can create hot spots
##### Hash-Based Sharding

- Distribute using a hash function
- Even distribution but harder to query ranges
##### Consistent Hashing for Resilient Hash-Based Sharding

- Traditional Hashing breaks when nodes are added/removed (re-hashing everything)
- Consistent Hashing solves this: Only a subset of keys need to be re-mapped when topology changes
- Enables better elasticity and fault tolerance
##### Geo-Based Sharding

- Shard by user region/location
- Useful in geo-distributed systems
### Polyglot Persistence

Using different types of DB for different components/services
#### Why?

Each DB excels at different things (search, analytics, relations)
#### Benefits:

- Better performance
- Optimized storage and queries
### Object Storage in Modern System

#### What is Object Storage?

A storage architecture that manages data as objects, not files or blocks
- Each object contains:
	- The data itself
	- A unique identifier (key)
	- Metadata
Unlike traditional storage, it is scalable, distributed and suited for unstructured data
### Key Concepts in Object Storage

- Object: Self-contained unit of data
- Bucket: Logical container for storing objects (like a folder)
- Metadata: Custom data that describes the object (eg: MIME type, timestamps, custom tags)
### Popular Object Storage Platforms

- Amazon S3
- Google Cloud Storage (GCS)
- Azure Blob Storage
- On-prem alternative (MinIO, Ceph)
### Common Use Cases

- Media storage
- Backups and archives
- Data lakes for analytics
- Static website hosting
- IoT and ML data pipelines
### Important Considerations with Object Storage

- Performance Considerations
	- Latency: Object storage has higher latency than block/file
	- Throughput: Designed for massive parallel access
	- Consistency: Eventual consistency in some platforms (e.g S3)
	- Access patterns: Suited for write-once, read-many workloads
- Cost Considerations
	- Storage class tiers: Standard, Infrequent Access Archive (eeg: S3 Glacier)
	- Charges: Storage, requests (PUT, GET), egress bandwidth
	- Best practices:
		- Use lifecycle rules for archiving/deletion
		- Monitor usage and optimize classes
### File Systems and Distributed Storage

- Defines how data is stored and retrieved on disk
- Eg: ext4, NTFS, XFS
- Handles file metadata, directories, permissions
### Key Characteristics of Traditional File Systems

- Hierarchical structure (folders/files)
- Limited scalability across machines
- Suited for single node systems
- Use cases: Personal devices, small servers
### What is a Distributed File System (DFS)?

- Allows file access across multiple nodes
- Ensures redundancy, fault tolerance
- Appears as a single file system to the user
- Key benefit: Scalability & Reliability
- Example:
	- HDFS (Hadoop Distributed File System)
	- Big Data Analytics
- Use Cases:
	- Big Data Analytics (eg: Hadoop, Spark)
	- Enterprise Storage (shared file system)
	- Scientific Computing
	- Media and Backup systems
### DFS Architecture and How Replication Works

- NameNode: Manages metadata, file hierarchy
- DataNodesL Store actual data blocks
- Replication across nodes for fault tolerance
- Data blocks are replicated across nodes
	- Ensures availability during node failures
	- Replication factor configuration
	- Example: HDFS default = 3 copiees
- Block size & striping concepts
### Scalability & Fault Tolerance

- DFS can scale horizontally by adding nodes
- Automatically rebalancing of data
- Supports high-throughput workloads
- Built-in failure recovery mechanisms
### Big Data

- Refers to datasets too large or complex for traditional data-processing tools
- Emerged due to growth in data generation from web, sensors, apps and machines
- Requires new storage, processing, and analysis strategies
### The 6 V's of Big Data

- Volume 
- Velocity
- Variety
- Veracity
- Value
- Variability
### Why Traditional Storage Fails at Scale

- Limited Scalability - not built for petabyte-scale data
- Performance bottlenecks - not optimized for parallel reads/writes
- Cost inefficiencies - expensive to scale up (vertical scaling)
- Lack of fault tolerance - no data replication or distribution recovery
### Common Big Data Workloads

- Logs & Events: App logs, system logs, server metrics
- Clickstreams: User navigation paths on website and apps
- IoT Data: Sensor streams, smart devices
- ML Pipelines: Feature extraction, model training, data versioning
### Batch vs Stream Processing

#### Batch Processing

Eg: Hadoop, Spark
#### Stream Processing

Eg: Apache Kafka, Spark Streaming, Flink

Batch: Historical Analysis, ETL Jobs, Nightly Aggregations
Stream: Real-time monitoring , fraud detection, recommendation systems
## System Performance

- Performance = How efficiently a system meets its functional requirements under load
- Key dimensions:
	- Speed: Time to respond
	- Capacity: Amount of work handled 
	- Efficiency: Resource usage under load
- Performance is not a single metric - it's a multi-dimensional goal
### Latency vs Throughput

- Latency 
	- Time taken to process one request 
	- Measured in ms or s
	- Affects responsiveness
- Throughput
	- Number of requests processed per sec
	- Measured in RDS or TPS
	- Affects scalability 
- Low latency not equals High throughput and vice versa
- Both must be balanced based on use case
### Scalability vs Responsiveness

- Scalability: Ability to handle increased load without performance degradation
	- Horizontal vs Vertical Scaling
- Responsiveness: System's ability to respond quickly
	- Tightly linked to latency
- Good design should ensure responsiveness at scale
### Measuring Performance

- Performance must be measurable & trackable:
	- SLA (Service Level Agreement): External contractual guarantee
	- SLO (Service Level Objective): Internal target
	- SLI (Service Level Indicator): Actual metric value
- Example:
	- SLA: 99.9% uptime
	- SLO: 95% of requests < 300ms
	- SLI: Actual measurement (eg, 93% of requests < 300ms)
### Understanding Percentiles

- Mean/average not equal useful in tail-latency-sensitive systems
- Percentiles provide better insight:
	- P50: Median
	- P95: 95% of requests faster than this
	- P99: Tail latency - critical for user experience 
- Track tail latencies for real-world performance insights
### Why Performance Matters in Modern Applications

- Users expect instantaneous responses (exp. mobile/web)
- Poor Performance leads to:
	- Drop-offs & bounce rates
	- Loss in revenue
	- System instability under load
- Performance is a feature, not an afterthought
- Impacts user experience, cost, and reputation
### Performance Testing Overview

- Types of performance testing:
	- Load Testing: Normal load conditions
	- Stress Testing: Beyond normal limits
	- Spike Testing: Sudden large load
	- Endurance Testing: Over extended time
- Goals:
	- Identify bottlenecks
	- Ensure reliability under real-world scenarios
### Introduction to Performance Monitoring

- Monitoring is not equal to testing - it's continuous
- Key tools:
	-  APM (eg: New Relic, Datadog)
	- Logs & Metrics (eg: ELK, Prometheus + Grafana)
- Track:
	- Latency & Throughput
	- Error Rates
	- Resource Usage (CPU, memory, DB queries)
## Why Caching Matters?

- Reduces latency by avoiding expensive re-computation or data retrieval
- Eases load on backend services and databases
- Improves user experience and system scalability
- Critical in low-latency, high-throughput architectures
### Types of Caching

- Client-side: Browser memory
- Server side: App level memory or in memory caches like Redis
- CDN caching: Static content cached close to users
- Database caching: Result-set caching, materialized views
### Caching Strategies

- Write-through: Write to cache and DB simultaneously
- Write-back (write-behind): Write to cache, DB is updated  asynchronous 
- Lazy loading (Cache-aside): Cache is populated only on demand
- Explicit/manual caching: Developer decides when to cache or evict
### Cache Eviction Policies

- LRU (Least Recently Used): Remove least recently accessed item
- LFU (Least Frequently Used): Remove least used item by count
- FIFO (First in, First Out): Remove oldest item added
- TTL (Time To Live): Automatically expire items after a fixed time duration
### Redis Overview

- In-memory key-value store for ultra-fast access
- Supports TTLs (time-to-live), pub/sub, persistence
- Used for caching, queues, sessions, leaderboards, etc
- Open-source, widely adopted
### Real-World Caching Examples

- CDN: Cache static assets (images, JS, CSS)
- Product page data: Cache popular catalog queries
- User sessions: Stored in Redis for fast access
- Search results: Frequently repeated queries cached
- API Response caching: Microservices avoid recomputation
## Messaging & Queues for Decoupling

### Why Use Asynchronous Messaging?

- Loose Coupling: Decouple producers from consumers
- Improved Performance: Producers don't block waiting for consumers
- Scalability: Consumers can scale independently
- Resilience: Message durability adds fault tolerance
- Flexibility: Easily add new consumers without changing producers
### Key Concepts of Messaging Systems

- Message: A data packet sent from producer to consumer
- Producer: Sends the message
- Consumer: Receives and processes the message
- Broker/Queue: Stores and delivers messages
- Topic/Queue: Logical channel for message delivery
- Ack: Acknowledgement of successful processing
### When to Use Queues in Architecture

- When workloads are bursty
- When you need decoupling between services
- For background jobs 
- For rate-limited or expensive operations
- To buffer spikes in traffic
### Popular Message Brokers: RabbitMQ vs Kafka

Use flexible routing and task queues
Use Kafka when you need durability, replays and 

- RabbitMQ is a message broker, while Kafka is a distributed streaming platform
### Delivery Guarantees

1. At-least-once (default in many systems)
	a. Message is retired until acknowledged
	b. May lead to duplicates
	c. Consumers must be indempotent
2. At most once
	a. Message sent only once
	b. No retries -> may result in message loss
3. Exactly once
	a. Guaranteed single delivery without duplicates
	b. Complex and more resource-heavy
	c. Kafka supports it under specific constraints
### Common Use Cases

- Order Processing
- Logging & Monitoring
- Monitor queue length & processing time
- Handle retries & failures gracefully
- Choose delivery semantics & failures gracefully
- Choose delivery semantics based on need
- Secure your message brokers (auth, encryption)
## Concurrency & Parallelism

*Concurrency* is when multiple tasks start, run and complete in overlapping time periods -- not necessarily simultaneously.

*Parallelism* is when multiple tasks are executed simultaneously, typically on multiple CPU cores.
### Processes vs Threads

#### Processes:

- Have their own space
- Heavier to create and switch 
- Isolated and safer
#### Threads:

- Share memory within a process
- Lightweight and faster
- Can lead to complex bugs (eg: race conditions)
### Thread Pools & Worker Models
#### Thread Pools

- Pre-created threads reused for multiple tasks
- Avoid overhead of creating/destroying threads
#### Worker Models

- Tasks are distributed to idle workers from a shared queue
- Improves scalability and CPU utilization
#### Example

- ASP.NET Core uses thread pool to handle requests efficiently
### Asynchronous Processing

#### Why Async

- Avoid blocking threads on I/O 
- Improve throughput
#### Techniques

- Async/Await (C#, JS)
- Promises, Futures
- Message Queues for background work
### Concurrency in Web Servers

- Traditional Servers (eg: Apache)
- Modern Servers (eg: Node.js, ASP.NET Core, Nginx)
### Common Pitfalls
#### Race Conditions

- Multiple threads access and modify shared data concurrently
- Causes unexpected behavior or corruption
#### Deadlock

- Two or more threads wait for each other to release resources
- System gets stuck indefinitely
### Best Practices

- Prefer async/non blocking I/O for I/O bound tasks
- Use thread pools instead of raw threads
- Always synchronize access shared data (locks, mutexes, etc)
- Detect and avoid deadlocks (lock ordering, timeout strategies)
- Real-World Examples
	- Web Server Handling 1000s of Requests: Uses thread pool + async I/0
	- Background Job Processing (eg: Email Queue): Worker model with RabbitMQ
	- Parallel Image Rendering: Each frame rendered in a different core
## Database Performance Optimization Techniques
### Replication

It is the process of copying and maintaining database objects in multiple databases
### Why Replicate

- High Availability: Ensure data availability in case of failure
- Load Balancing: Distribute read traffic across multiple servers
- Disaster Recovery: Maintain copies of data across different locations
### Types of Replication

- Master-Slave Replication: One primary database, multiple replicas for reads
- Master-Master Replication: Multiple primary databases, often used for writes and redundancy
### Sharding & Partitioning Strategies Recap
#### Sharding

- Splitting large datasets into smaller, more manageable pieces
- Distribute data across multiple servers for better performance and scalability
- Example: User data across multiple shards based on geographical region
#### Partitioning

- It is the division with a single database into separate tables or partitions
- Types:
	- Range: Split data by a range
	- Hash: Split data by hashing
### CAP Theorem (Performance Focus)

- Consistency
- Availability
- Partition Tolerance
### Indexes

It is a data structure that improves query performance by reducing the amount of data scanned
#### Types of Indexes:

- B-Tress Indexes: Common for exact match and range queries
- Hash Indexes: Best for equality comparisons
- Full-Text Indexes: Used for searching large textual data
- Bitmap Indexes: Suitable for low cardinality columns (e: gender)
#### When to Use Indexes

- Read-heavy operations: Indexes speed up query performance
- Write heavy systems: Be cautious, as indexes can slow down inserts and updates
### Normalization and Denormalization

Normalization: Reduces data redundancy by organizing data into tables (Transactional Systems)
Denormalization: Introduce redundancy to reduce join operations and speed up reads ( Reporting Systems)
### Connection Pooling

A technique used to manage database connections efficiently by reusing established connections instead of creating new ones

It reduces overhead caused by frequent connection creation and teardown

Helps handles a large number of concurrent connections effectively
### Query Optimization

The process of improving the performance of SQL queries
#### Techniques

- Use of indexes: Leverage indexes to speed up search operations
- Avoiding N+1 queries: Reduce unnecessary database hits by using joins or batching queries
- Using Proper Joins: Minimize complex joins when possible
### Materialized Views

- A precomputed query result stored as a table
#### Benefits

- Speeds up query performance by avoiding real time computation
- Useful in reporting and data warehousing
#### Use Cases

- Data aggregation or summer data that doesn't change frequently
- Reporting systems where fast retrieval is critical
### Batching 

- Sending multiple operations in a single request or transaction to reduce overhead
- Use Case: Bulk inserts or updates
### Pagination

- Definition: Breaking large sets of data into smaller chunks for efficient retrieval
- Prevents large queries that could lead to timeouts or memory issues
- Ensures responsive UI by fetching data incrementally
## System Reliability

*Systems fail. Reliability is how gracefully they handle it*

It is the ability of a system to operate continuously without failure
It includes:
- Correctness
- Consistency
- Fault Tolerance
- Uptime
### Key Metrics - MTBF & MTTR

- MTBF: Mean Time Between Failures - Average time a system works before failing
- MTTR: Mean Time To Recovery - Avg. time to recover from failure

*High MTBF + Low MTTR = High Reliability*
### SLAs

It is a contractual guarantees about system performance

- Availability 
- Response Time
- Error Rate

99.9% uptime = ~8.76 hours of downtime/year
### Availability vs Durability

- Availability: System is accessible and responsive
- Durability: Data is safe and not lost
## High Availability, Fault Tolerance & Failover

- Redundancy is crucial to ensuring system reliability and availability.
- Purpose: Prevent single points of failure.
- Types of redundancy:
	- Hardware (servers, storage)
	- Network (network routes, paths)
	- Services (microservices, databases)
### N+1, Active-Active vs Active-Passive

- N+1 Redundancy: One extra instance (eg, 3 instances for 2 required)
- Active-Active: Multiple nodes work together, each handling requests
- Active-Passive: One active node, others are standby, only activated on failure
### Graceful Degradation

- Graceful Degradation: System still operates at a reduced capacity during failures
- Helps maintain user experience even when full service isn't possible
- Critical for ensuring users still benefit from some functionality during outages
### High Availability Patterns in Real-World Systems

- Load Balancers:
	- Distribute traffic evenly across healthy nodes.
	- Essential for active-active configurations
- Replication: Copy data across multiple nodes or data centers for availability 
- Failover: Automatically switch to a backup node/service in case of failure
### Designing for Redundancy 

- Redundancy Components: Design with multiple instances of key components (servers, databases, etc) to avoid failure.
- Geographical Redundancy: Use multiple data centers or cloud regions for disaster recovery.
- Automated Failover: Ensure failover happens automatically without manual intervention.
### Health Monitoring & Self-Healing Systems

- Health Monitoring:
	- Track the status of system components (eg servers, services)
	- Alerts for system failures or performance degradation
- Self-Healing Systems:
	- Automatically repair or replace failed components.
	- Commonly used in cloud environments for fault tolerance
## Backup & Recovery

### Types of Backup

- Full Backup
- Incremental Backup
- Differential Backup
### Recovery Types (Cold, Warm, Hot)

- Cold Recovery
	- Backups stored offline
	- High downtime, low cost
- Warm Recovery
	- Some resources pre-provisioned
	- Moderate downtime and cost
- Hot Recovery
	- Fully redundant, Always ready
	- Minimal downtime, highest cost
### Tradeoffs in backup strategy

- Business criticality
- Compliance needs
- Infrastructure maturity
### Best Practices

- Automate backups and testing of restores
- Encrypt backups at rest and in transit
- Monitor backup success & failure
- Apply 3-2-1 Rule:
	- 3 copies
	- 2 different mediums
	- 1 offsite
### Disaster Recovery Matters

- Downtime costs
- Protects against regional outages, data loss, cyber attacks
- Complements backup strategies with full system level resilience
- Required for compliance in regulated industries
### DR for Mission Critical Apps

- System must meet strict RTO & RPO targets
- Requires redundancy at multiple levels: compute, storage, network
- Automated failover + tested recovery plan
- Eg: banking, healthcare, e commerce
### Failover + Backup = True Resilience 

- Backup alone = data recovery
- Failover = service continuity
- Combine both:
	- Backups for corruption or deletion
	- Failover for infra or region outage
- Include both in DR plan for full coverage
### Testing & Automation

- DR plans must be tested regularly
- Automate:
	- Failover switching 
	- Data validation after restore
	- Notifications & logging
- Run DR drills: simulate failures
- If you haven't tested it, you don't have it
### Challenges in Geo-Distributed Systems

- Data consistency across regions
- Latency during sync and failover
- Regulatory constraints (data locality)
- Coordinating multi-region failovers
### Geo-Redundancy & Quorum-Based Design

- Geo-redundancy: deploy across multiple physical locations
- Quorum-based design: Quorum is the minimum number of servers that must acknowledge a distributed operation to be successful before its marked a success
- This ensures:
	- Data consistency
	- Safe failover (majority nodes available)
## Security 
### Why security matters in system design?

- Security is a non functional requirement but critical for:
	- User trust
	- Data protection
	- System reliability
- Examples: Data breaches(Equifax, Facebook, etc)
### Why is Security in Distributed Systems?

- Distributed systems: more entry points, more vulnerabilities
- Security Considerations
	- Data in transit & at rest
	- Authentication, Authorization
	- Secure APIs & endpoints
	- Node and network level protection
### The CIA Triad

- Confidentiality
- Integrity
- Availability
### Threat Modeling: Understanding Your Adversary

- Define potential attackers and what they want
- Consider:
	- Attack surface
	- Entry points
	- Assets to protect
- Tools: STRIDE model (Spoofing, Tampering, Repudiation, Info disclosure, Denial of service, Elevation of privilege)
### Common Attack Vectors

- How attackers get in:
	- Insecure APIs
	- Misconfigured servers
	- Poor authentication
	- Open ports/services
### Common Attacks

- DDoS
- MITM
- Injection (SQL Injection)
- Spoofing Attacks
### Security in the Software Development Cycle (SDLC)

- Embed security from the start (Shift Left)
- Phases:
	- Requirements: Threat modeling
	- Design: Secure Architecture
	- Development: Secure coding
	- Testing: Security tests, fuzzing
	- Deployment: Secrets Management
	- Maintenance: Patch Management
### Best Practices

- Adopt security by design
- Use encryption (TLS, at-rest)
- Harden infrastructure (firewalls, VPCs)
- Validate inputs and sanitize outputs
- Monitor and log activity
### Authentication & Authorization

Understand clearly the difference between both
### Common Authentication Methods

- Basic Authentication: Simpler user and password based
- OAuth2: Delegated access protocol, allowing third party services to access user data without exposing creds
- OpenID Connect: An identity layer built on top of OAuth2 for auth, often for single sign-on (SSO)
- JWT (JSON Web Tokens): Token based auth, commonly used in stateless apps and APIs
### Session based vs Token based Auth

- Session based Auth: Server-side storage of session data, typically using cookies
	- Pros: Easy to implement, works well with traditional web apps
	- Cons: Scalability challenges in distributed systems
- Token-based Auth: Stateless, where tokens (eg: JWT) are used to authenticate the user.
	- Pros: Scalable, decouples backend systems.
	- Cons: Requires secure token storage and handling
### Access Control Models

- RBAC Role
- ABAC Attribute
- DAC Discretionary
- MAC Mandatory
### SSO and Identity Federation

- SSO: A user auth process that allows a user to access multiple apps with a single set of creds
	- Benefits: User convenience, reduced password fatigue
- Identity Federation: A system where multiple identity providers (eg: Google, Facebook) can be used to authenticate users across different platforms.
	- Benefits: Seamless user exp across different services, reduces need for creating multiple accounts.
## Data Protection & Secure Communication

### Why Data Protection Matters

- Growing threats: breaches, mitm attacks, data leaks
- Regulations (GDPR, HIPAA, etc)
- User trust and system reliability
### Encryption

- Plaintext -> Ciphertext -> Decryption
- Key = secret for encoding/decoding
### Encryption at Rest and Transit

- Encryption at Rest
	- Protects stored data
	- Common techniques: Full-disk encryption, database-level encryption
	- Use Cases: Cloud storage, user files, logs
- Encryption in Transit
	- Secures data during transmission (eg: HTTP request/response)
	- TLS/SSL protocols enable secure communication
	- Must have for APIs, user sessions 
### Symmetric vs Asymmetric Encryption

- Symmetric: One key (fast, used for large data)
- Asymmetric: public/private key pair (secure key exchange)
- Often used together (eg: TLS handshake)
### TLS/SSL and HTTPS

- HTTPS = HTTP over TLS
- Ensures confidentiality, integrity, and authenticity
- TLS handshake: key exchange + cipher negotiation
### Hashing and Salting Passwords

- Hashing = one-way transformation
- Use for storing passwords (not reversible)
- Salting: add random data to prevent rainbow table attacks
### Public Key Infrastructure (PKI)

- PKI = system for managing digital certificates and keys
- Role of Certificate Authorities (CAs)
- Digital signatures & certificate chains
### Secure API Communication

- Use HTTPS for all API traffic
- Auth tokens (JWT, OAuth)
- Rate limiting, IP whitelisting, mutual TLS for sensitive APIs
## Network Security

- External threats
- Internal Risks
- Increasing cloud native adoption = more exposure
- Reliability & user trust 
### Firewalls and Reverse Proxies

- Firewalls: filter traffic based on IP, port, protocol
- Types: Network-based, Host-based, Cloud firewalls
- Reverse Proxies: route, mask backend identity, add security
- Examples: NGINX, AWS ALB
### Rate Limiting, Throttling, IP Filtering

- Rate limiting: per-user, per-IP request caps
- Throttling: graceful degradation under load
- IP Filtering: allow/block lists
- Helps protect APIs & backend systems from abuse
### Network Segmentation & Isolation

- Split network into zones: DMZ, internal, DB, etc
- Limit lateral movement
- Use firewalls, subnets, private VLANs
- Cloud: use VPCs, security groups, NACLs
### Zero Trust Security Model

- "Never trust, always verify"
- Auth every request, even inside the network
- Microservices: mutual TLS, strict access control
- Applies to cloud, hybrid, and on prem setups
### Securing Cloud Environments

- Shared responsibility model
- Key aspects
	- IAM
	- Encryption
	- Audit logging
- CSPM (Cloud Security Posture Management) tools
### Securing Serverless & Containerized Workloads

- Serverless: control IAM roles, timeouts, API gateway access
- Containers: image scanning, runtime hardening, least privilege
- Tools: AWS Lambda + API Gateway, Docker + Kubernetes security tools (OPA, Falco)
### Security in Microservices

- Service to service auth (JWT, mTLS)
- API Gateway security: validation, auth, rate limits
- Service mesh: fine-grained, TLS, policies (Istio, Linkerd)
### Common Vulnerabilities (OWASP Top 10)

- A quick glance at top risks
	- Injection
	- Broken Auth
	- Sensitive Data Exposure
	- Security Misconfig
	- XSS, CSRF, SSRF, etc
- Relevance in web apps & microservices
- Focus on awareness + mitigation
## The System Design Blueprint

- Practicality
- Accuracy
- Efficient
- Reliability
- Optimization
- Scalable
### The 4 steps process

- Understanding the problem & defining the scope
- Estimating scale & identifying bottlenecks
- High level design: services, apis & communication
- Making tech & infra decisions strategically