# Couchbase Basics

## Properties

- **Memory first architecture**
- **Distributed database**
- **Scalability**
- **Fault tolerance (using replication)**


## Concepts
- **Clusters**
    - A Couchbase cluster is a collection of one or more nodes (servers) that work together to manage and store data.
    - A cluster is like a team of workers in a warehouse. If you need to store or retrieve items, different workers handle different sections (nodes), ensuring that the workload is balanced. If one worker gets sick (a node goes down), other workers can step in to handle that section, so the operation continues smoothly.
    - It prkey features of clusters include **high availability**, **fault tolerance**, and **scalability**.

- **Nodes**
    - A node in Couchbase is an individual server that is part of a cluster.
    - Each node can be compared to a worker in a team (cluster). Each worker is responsible for a specific task (data storage, indexing, etc.). If one worker fails, others can take over the missing responsibilities (through replication and high availability features).
    - The key features of node includes **data storage**, **Services**, **Replication**, and **Fault Tolerance**

- **Data**
    - Json document
    - Key value
    - Flexible schema
    - Dynamic schema
    - N1QL support

- **Buckets**
    - Like database in SQL
    - For segregation of different data
    - At max 10 buckets in couchbase
    - In a bucket data is stored in documents

- **VBuckets**
    - Virtual buckets inside buckets
    - For further segregation of data
    - By fault 1024 VBuckets created by couchbase 
    - distributed over the cluster

- **Compression**
    - Data written in RAM by default is in originalk size.
    - Can be opt to compression via config.
    - After crossing threshold Data from RAM is moved to Disk.
    - In Disk compression is by force.

- **Expiration**
    - **TTL** time to live is expiration period defined to a data.
    - can be defined a bucket level or document level.
    - After expiry data is marked as **Soft Delete**.
    - Data is deleted when a Soft Delete Data is requested
    - Data is deleted by **Pager Expiry** process which checks for data to delete in regular intervals.

- **Memory & Storage**
    - Data written into RAM first.
    - Writing thus is very fast.
    - In background a async process moves the data into disk.
    - When reading data is equired from RAM.
    - RAM returns data if present.
    - If not data fetched from disk decompressed sent to RAM and then returned.
    - Reading thus next time would be very fast.

- **Index**
    - **Primary Index**
    - **Secondary Index**
    - **Composite Secondary Index**
    - **Full Text Index**
    - **Array Index**

- **Views** 
    - Like in SQL.

- **Services**
    - **Data Service** - RAM and Discs to manage data
    - **Query Service** - N1QL (SQL) support
    - **Index Service** - manages different indices.
    - **Search Service** - for Full Text Index
    - **Analytic Service** - Complex query, aggregation, joins etc. 

- **Limits**
    - max size for a key is 250 bytes.
    - max size for a value is 20 MB.
    - recommended no of nodes in a cluster is 3.
    - max count od buckets is 10.



