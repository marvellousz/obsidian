### Why do Systems Need to Scale?

- User base grows
- Increasing data volume
- Peak events
- Avoid service degradation or downtime
- Meet performance SLAs
### Types of Scalability 

- Vertical Scalability: Add more CPU/RAM to one server
- Horizontal Scaling: Add more servers to distribute the load
### Common Challenges in Scaling

- Latency
- Bottlenecks
- Downtime
- Cost
### Types of Scalability

1. [[Vertical Scalability]]
2. [[Horizontal Scalability]]
3. [[Diagonal Scalability]]
### Trade-Offs: Cost vs Complexity vs Performance

Strategy     Cost        Complexity     Performance
Vertical       Low-mid Low                Medium
Horizontal  High        High              High
Diagonal     Medium  Medium        High

### Real-World Examples and When to Choose What?

- Examples:
	- Twitter: Moved from monolith -> horizontal scaling (microservices)
	- Small startups: Vertical scaling for MVP
	- AWS Lambda apps: Start diagonal with autoscaling
- When to choose:
	- Startups: Vertical (cheaper, simpler)
	- Scaling apps: horizontal (resilience + capacity)
	- Cloud-native: diagonal (flexibility + cost balance)

Vertical = simpler, but hits limits
Horizontal = scalable, but needs planning
Diagonal = hybrid approach for cloud success