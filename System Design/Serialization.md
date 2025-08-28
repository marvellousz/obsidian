- Apps need to exchange & store structured data efficiently.
- Serialization converts complex objects into a format that can be easily transferred.
- Used in APIs, databases, caching, and distributed systems.
## What is Serialization?

- Converting objects into a format for transmission/storage
- Deserialization is the process of converting it back into an object
- Essential for distributed systems & inter-process communication
## Common Serialization Formats

- JSON - Human-readable, widely used in REST APIs
- XML - Structured but verbose, used in legacy systems
- Protocol Buffers (Protobuf) - Compact & efficient, used in gRPC
## Trade-offs

- Readability: JSON & XML are human-readable, but inefficient
- Efficiency: Protobuf & Avro are compact, reducing bandwidth usage
- Compatibility: XML support schema evolution, JSON has limited support
## Serialization

- Serialization in APIs
	- Rest APIs mostly used JSON
	- gRPC APIs use Protobuf for efficiency
	- XML is still used in SOAP-based web services
- Serialization in Caching & Data Storage
	- Redis & Memcached: Store serialized JSON/Protoobuf data
	- Databases: NoSQL databases like MongoDB use BSON (Binary JSON)
	- Big Data: Protobuf used for efficient storage & schema evolution
## Performance Considerations

- Serialization choice impacts Bandwidth, CPU, and Memory Usage
- JSON/XML -> Larger payloads, slower parsing
- Protobuf -> Smaller payloads, faster parsing but needs schema