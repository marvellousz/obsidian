# Caching Concepts

## 1. Caching
Caching is a technique to store frequently accessed data in a faster storage medium (e.g., memory) to reduce retrieval time and improve system performance. It acts as a buffer between the application and slower storage (e.g., disk or network).

---

## 2. Hit and Miss Ratio
- **Cache Hit**: Occurs when the requested data is found in the cache.
- **Cache Miss**: Occurs when the requested data is not in the cache, requiring retrieval from slower storage.
- **Hit Ratio**: The percentage of cache hits compared to total requests:
 ![[Pasted image 20241206151813.png]]
 
- **Miss Ratio**: Complement of the hit ratio, calculated as:

![[Pasted image 20241206151843.png]]

---

## 3. Memory vs. Disk Caching
- **Memory Cache**: Stores data in RAM for faster access but has limited capacity.
- **Disk Cache**: Uses part of the disk to store frequently used data. It's slower than memory but provides larger storage.

---

## 4. Write Policies
- **Write-Around Cache**:  
  Writes data directly to the slower storage, bypassing the cache. This avoids polluting the cache with data that may not be reused soon.
  
- **Write-Back Cache**:  
  Writes data to the cache first and defers writing to the slower storage until necessary. It improves write performance but risks data loss during a cache failure.

---

## 5. Eviction Policies
When the cache is full, older or less-used data is evicted to make room for new data. Common eviction policies include:

- **FIFO (First-In, First-Out)**:  
  Removes the oldest data in the cache.

- **LRU (Least Recently Used)**:  
  Evicts the data that has not been accessed for the longest time.

- **LFU (Least Frequently Used)**:  
  Removes data that has been accessed the least number of times.



