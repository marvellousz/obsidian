It is a software design pattern where apps are structured as a collection of small, loosely coupled services, each responsible for a specific function.
## Characteristics

- Independently deployable services
- Loosely coupled & modular
- Scalable & fault-tolerant
## Identifying and Structuring Microservices

- How to identify Microservices?
	- Business Capabilities
	- Single Responsibility Principle
	- Data Ownership
	- Independently Deployable
- How to Structure Microservices
	- Decompose to Business Domain
	- Define Clear APIs
	- Choose the Right Granularity
	- Implement Observability
## Communication in Microservices

- Synchronous Communication
	- Rest APIs
	- gRPC
- Asynchronous Communication
	- Event-Driven Messaging (Kafka, RabbitMQ, SNS/SQS)
## Challenges of Microservices

- Data Consistency
- Distributed Tracing
- Network Overhead
- Security
## Scaling Strategies in Microservices

- Horizontal Scaling 
- Auto Scaling
- Sharding & Database Scaling: Split databases for high-traffic services