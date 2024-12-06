# Consistent Hashing

## 1. What is Consistent Hashing?
**Consistent hashing** is a distributed hashing technique designed to evenly distribute data across nodes in a system while minimizing disruption when nodes are added or removed. It is widely used in distributed systems such as caching, load balancing, and distributed databases.

---

## 2. How Does It Work?

### Key Concepts:
1. **Hash Ring**:  
   - Consistent hashing maps both nodes (e.g., servers) and keys (e.g., data items) to a circular hash space (e.g., values from 0 to \(2^{32} - 1\)).
   - Each node is assigned a position on the ring based on a hash function.

2. **Key Assignment**:  
   - Each key is assigned to the first node encountered while traversing the hash ring clockwise from the key’s hash position.
   - This ensures that each key is assigned to exactly one node.

3. **Node Addition/Removal**:  
   - When a node is added, only the keys falling between the new node and its predecessor are reassigned to the new node.
   - When a node is removed, its keys are reassigned to its successor on the ring.
   - This minimizes disruption compared to traditional hashing, where adding or removing a node can reassign all keys.

---

## 3. Example

### Initial Setup:
- **Nodes**: \(N1, N2, N3\)  
- **Keys**: \(K1, K2, K3\)  
- **Positions on the Hash Ring**:
  - \(N1\): \(0\)
  - \(N2\): \(120\)
  - \(N3\): \(240\)

### Key Assignments:
- \(K1 = 10 \rightarrow N1\) (Closest node clockwise)
- \(K2 = 130 \rightarrow N2\)
- \(K3 = 250 \rightarrow N3\)

### Adding a New Node:
- Add \(N4\) at position \(60\).  
- Keys in the range \(N1 \rightarrow N4\) (e.g., \(K1\)) are reassigned to \(N4\). Other keys remain unchanged.

### Removing a Node:
- Remove \(N2\).  
- Keys in the range \(N2 \rightarrow N3\) (e.g., \(K2\)) are reassigned to \(N3\).

---

## 4. Virtual Nodes
**Virtual nodes** address the problem of uneven load distribution caused by nodes having different capacities or uneven hashing:

- Each physical node is assigned multiple **virtual nodes**.
- Virtual nodes are distributed across the hash ring to balance the load.
- Example:
  - Node \(N1\) could have virtual nodes \(VN1-1\), \(VN1-2\), \(VN1-3\).
  - Node \(N2\) could have virtual nodes \(VN2-1\), \(VN2-2\).

---

## 5. Advantages
- **Minimal Disruption**:  
  Only a small fraction of keys are reassigned when nodes are added or removed.  
- **Load Balancing**:  
  Distributes keys evenly across nodes, especially with virtual nodes.  
- **Scalability**:  
  Handles dynamic changes in the number of nodes efficiently.  
- **Fault Tolerance**:  
  Redistributes keys seamlessly when nodes fail.

---

## 6. Applications
- **Distributed Caching**: Systems like Memcached and Redis clusters use consistent hashing to distribute data.  
- **Load Balancing**: Distributes requests evenly across servers in web server clusters.  
- **Distributed Databases**: Used in systems like Cassandra, DynamoDB, and Amazon S3 for data partitioning.

---
