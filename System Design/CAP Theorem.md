## 1. What is the CAP Theorem?

The **CAP theorem**, proposed by Eric Brewer, states that a distributed system can guarantee only two out of three properties at any given time:

1. **Consistency (C)**:  
   - All nodes in the system see the same data at the same time.  
   - Example: After a write operation, a read from any node should return the same updated value.

2. **Availability (A)**:  
   - Every request receives a response, whether successful or not.  
   - Example: The system remains operational, even if some nodes fail.

3. **Partition Tolerance (P)**:  
   - The system continues to operate despite network partitions (communication breakdowns between nodes).  
   - Example: Data replication across geographically distributed servers remains functional even with network failures.

---

## 2. Key Insights of the CAP Theorem

- A distributed system must tolerate **partitions**, as network failures are unavoidable. Therefore, systems must choose between **Consistency** and **Availability** during a partition.
- **Trade-offs** are necessary, depending on the system's requirements.

---

## 3. CAP Trade-offs

| Guarantee         | Description                                                                                      | Example Systems                              |
|-------------------|--------------------------------------------------------------------------------------------------|---------------------------------------------|
| **CP (Consistency + Partition Tolerance)** | Ensures consistent data but sacrifices availability during partitions.                            | HBase, MongoDB (configured for CP).         |
| **AP (Availability + Partition Tolerance)** | Ensures availability of the system but sacrifices consistency during partitions.                  | DynamoDB, Cassandra, Couchbase.             |
| **CA (Consistency + Availability)**        | Ensures consistency and availability but cannot handle network partitions (not practical for distributed systems). | Relational databases (on a single server). |

---

## 4. Examples of CAP in Action

### CP System Example:
- **HBase**: During a network partition, HBase prioritizes consistency by rejecting operations on unreachable nodes, sacrificing availability.

### AP System Example:
- **Cassandra**: During a network partition, Cassandra prioritizes availability by allowing nodes to serve requests with potentially stale data, sacrificing consistency.

### CA System Example:
- **MySQL**: On a single server (no partition tolerance), MySQL ensures strong consistency and availability.


