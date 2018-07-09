---
layout: layout.pug
navigationTitle: Couchbase 0.1.0-5.1.0
title: Couchbase 0.1.0-5.1.0
menuWeight: 50
excerpt: Overview of DC/OS Couchbase 0.1.0-5.1.0
featureMaturity:
enterprise: false
---



Couchbase Server, originally known as Membase, is an open-source, distributed (shared-nothing architecture) multi-model NoSQL document-oriented database software package that is optimized for interactive applications. These applications may serve many concurrent users by creating, storing, retrieving, aggregating, manipulating and presenting data.

It is designed to be clustered from a single machine to very large-scale deployments spanning many machines.


## Benefits of Couchbase
1. It is Open Source and schema free.
2. High performance, managed cache and straming replication and indexing.
3. Supports multiple data centers, Big Data and SQL Integrations.
4. An embedded DB (Couchbase Lite) for iOS and android.
5. Couchbase is distributed and fault tolerant.
6. Container and Cloud Deployments.
7. High Availability.
8. Memory-first Architecture.


## DC/OS Couchbase provides the following features:
1. Unified Programming Interface: The Couchbase Data Platform provides simple, uniform and powerful application development APIs across multiple programming languages, connectors, and tools that makes building applications simple and accelerates time to market for applications.
2. Analytics: Couchbase Analytics provides powerful parallel query processing. Designed to efficiently execute complex, long-running queries that contain complex joins, set, aggregation, and grouping operations. Addresses the challenges of supporting responsive, scalable apps and ad hoc analytics on the same dataset.
3. Scale out architecture: Couchbase is designed to scale easily on commodity hardware and to be more hardware efficient than other NoSQL databases. Replication and sharding are fundamental features of Couchbase Server. It automatically distributes data across nodes in the cluster. Thus, the database can grow horizontally to share load by adding more RAM, disk, and CPU capacity without increasing the burden on developers and administrators.

## Components/Services
Couchbase is designed to scale easily on commodity hardware and to be more hardware efficient than other NoSQL databases. Replication and sharding are fundamental features of Couchbase Server. It automatically distributes data across nodes in the cluster. Thus, the database can grow horizontally to share load by adding more RAM, disk, and CPU capacity without increasing the burden on developers and administrators. Couchbase Server achieves high hardware efficiency by employing asynchronous, non-blocking I/O at all levels for effective utilization of server resources. This maximizes both the storage I/O and the number of simultaneously connected clients per node. Couchbase’s architecture ensures that workloads are evenly distributed across cluster nodes, reducing bottlenecks and allowing users to take full advantage of the available hardware.

Customers expect and demand fast, responsive applications. The Couchbase Data Platform provides an architecture where performance is paramount, ensuring that all operations occur in memory and providing special memory-optimized data management options. Couchbase is designed to process online operational data-heavy read and write traffic for large modern web, mobile, and IoT applications. For Couchbase, low latency at scale typically refers to consistent sub-millisecond reads and writes. While maximum raw speeds are important, many practitioners care more about being able to deliver those high speeds and low latencies with minimal variance during heavy workloads. Couchbase continues to deliver consistently high performance even under heavy load. Predictable, consistent performance guarantees responsiveness and improves the user experience in real-world deployments.
