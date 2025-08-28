A system design where components communicate through events rather than direct calls.
## Key Characteristics

- Asynchronous Processing
- Loose Coupling
- Scalability & Flexibility
## Why Use It?

- Enhances system responsiveness
- Enables real-time event processing
- Supports complex workflows
## Synchronous & Asynchronous Systems

- *Synchronous Communication* : Request-Response Model
- *Asynchronous Communication*: Event-Driven Model
## Pub-Sub vs Event Streaming

- Pub-Sub Model
	- Events are broadcasted to multiple subscribers
	- Each subscriber gets the event once
	- Eg: RabbitMQ, AWS SNS
- Event Streaming
	- Events are stored & consumed in order
	- Consumers process events at different times
	- Eg: Kafka, AWS Kinesis
## Key Components of an Event-Driven System

- Event Producers (Generate Events)
- Event Brokers (Transmit & store events) - Eg: Kafka, RabbitMQ, AWS EventBridge
- Event Consumers (React to events)
- Event Storage (Log-based persistence for replaying events)
## Challenges in Event-Driven Architecture

- Eventual Consistency
- Ordering Guarantees
- Fault Tolerance & Retires
- Debugging Complexity
## Best Practices

- Use idempotent event processing to avoid duplicates
- Implement dead-letter queues for failed messages
- Choose the right event broker based on system needs
- Ensure event versioning to handle schema changes
## Use Cases of Event-Driven Architecture

- Logging & Auditing 
- Real-Time Notifications
- Microservices
- IoT Systems
- E-commerce Order Processing 
