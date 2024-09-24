## 1. Introduction

Kafka is an event streaming platform which can collect, process, store and integrate data at scale.
Use cases:
* Distributed streaming
* Stream processing
* Data integration
* Pub/Sub Messaging

Kafka works with events that occur in any software application.
#### 1.1 Event

An event is any type of action or change that is identified by software. Example: Payment, click, reading etc. 
This is usually represented in a structured format: 
* JSON
* Protocol Buffer

Here are some key points for how Kafka processes events:
* Kafka stores events as key/value pairs.
* Every key/value pair is stored as bytes in Kafka.
* The process of converting bytes to structured data is called serialization/deserialization.

## 2. Kafka Architecture

#### 2.1 Kafka Topics

A topic is a fundamental unit of organisation in Kafka. Similar to a table in a relational DB. 
* Different topics hold different events
* Different topics hold filtered and transformed versions of Kafka
Properties of a topics:
* Topic is a log of events
* Topics are append only (always added to the end)
* Read operation by setting an offset and scanning sequential entries
* Events in the log are immutable
* Topics can be configured to expire data after it reaches a certain age or size
#### 2.2 Kafka partitioning

Partitioning breaks a topic log into multiple logs which can live on separate nodes in a Kafka cluster. Hence storing messages, writing new messages and reading old messages can be distributed across a cluster.

How it works:
* If a message has no key, subsequent messages will be written in a round robin manner among all partitions.
* If a message has a key, then destination partition is computed from the hash of the key, hence all messages with the same key will be stored in the same partition and in order.
#### 2.3 Kafka Brokers and replication

Kafka is composed of a network of physical machines or containers called brokers. Essentially they are independent machines running the Kafka broker process. Each broker hosts some set of partitions and handles the read/write events. For data reliability the partition data is copied to other brokers to keep safe. Copies are called follower replica. Main partition is called leader replica. Reading/writing is done to the leader replica, then the leaders and followers work together to replicate the new writes.

* This is usually something the developer does not have worry about, durability guarantees can be tuned though.

#### 2.4 Client

Producers and Consumers use the Kafka cluster. They contain the code to read and write events to the Kafka topics in the cluster.

* Producer writes to a topic in the cluster
* Consumer reads from a topic in the cluster

#### 2.5 Kafka Producer

* API interface with a "Producer Class" which takes configuration parameters like addresses of brokers to connect to a cluster.
* API interface with a "Producer Record class" which holds a key/value pair which is written to a cluster.

#### 2.6 Kafka Consumer

* API interface with "Consumer Class" to connect to a cluster.
* Using the connection one can subscribe to many topics.
* API interface for "Consumer Record Class" which represents key/value pair for reading Kafka messages.



