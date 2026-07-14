# Technical Questions and Answers

## 1. Adhikya Edammala

### What is the use of a `docker-compose` file?

A `docker-compose.yml` file is used to define and run multiple Docker containers together.

It can specify:

* Services
* Docker images
* Ports
* Environment variables
* Networks
* Volumes
* Service dependencies

For example, a single Docker Compose file can start an application, database, and Redis server using:

```bash
docker compose up
```

---

## 2. Allanki VV Manikanta Sai

### What is the default Redis port?

The default Redis port is:

```text
6379
```

---

## 3. Arpit Yadav

### What is an AI agent?

An AI agent is a software system that:

* Observes information
* Makes decisions
* Performs actions
* Works toward a specific goal

An AI agent may use:

* AI models
* APIs
* External tools
* Memory
* Databases

For example, an AI travel agent can search for flights, compare prices, and prepare a travel itinerary.

---

## 4. Boorle Sowmya Sri Lakshmi

### What are routing keys and binding keys in RabbitMQ?

A **routing key** is attached to a message by the publisher.

A **binding key** is used when connecting a queue to an exchange.

The exchange compares the routing key with the binding key to determine which queue should receive the message.

Example:

```text
Routing key: order.created
Binding key: order.created
```

When the keys match, the message is routed to the corresponding queue.

---

## 5. Naman Sharma

### What is BSON in MongoDB?

BSON stands for **Binary JSON**.

MongoDB uses BSON to store documents internally.

BSON supports more data types than regular JSON, including:

* Date
* ObjectId
* Binary data
* Decimal
* Integer types

Example MongoDB document:

```json
{
  "name": "Musharaf",
  "age": 25
}
```

---

## 6. Nayunipatruni Harsha Vardhan

### What data structures does Redis support?

Redis supports several data structures, including:

* Strings
* Lists
* Sets
* Sorted sets
* Hashes
* Streams
* Bitmaps
* HyperLogLogs
* Geospatial data

For example:

* **Hashes** can store user information.
* **Lists** can be used to implement queues.
* **Sets** can store unique values.
* **Sorted sets** can be used for leaderboards.

---

## 7. Parlapalli Sulochana

### Can a publisher directly send messages to a consumer in RabbitMQ?

No. A publisher normally sends a message to an **exchange**, not directly to a consumer.

The message flow is:

```text
Publisher → Exchange → Queue → Consumer
```

The exchange routes the message to one or more queues, and consumers receive messages from those queues.

---

## 8. Rongala Vasu

### What is a volume in Docker?

A Docker volume is persistent storage used by Docker containers.

Container data may be lost when a container is removed. A volume stores the data outside the container lifecycle, allowing the data to remain available even when the container is recreated.

Example:

```yaml
services:
  mysql:
    image: mysql
    volumes:
      - mysql_data:/var/lib/mysql

volumes:
  mysql_data:
```

In this example, the MySQL database data is stored in the `mysql_data` volume.

---

## 9. Rovinpal Udupi

### What is replication in a database?

Database replication means copying data from one database server to one or more other servers.

Replication is commonly used for:

* High availability
* Disaster recovery
* Read scalability
* Data backup
* Automatic failover

For example, a primary database handles write operations, while replica databases maintain copies of the data and may handle read operations.

---

## 10. Vikas Mehta

### Why do we use Kubernetes?

Kubernetes is used to deploy, manage, and scale containerized applications.

It provides features such as:

* Automatic container deployment
* Horizontal scaling
* Load balancing
* Self-healing
* Service discovery
* Rolling updates
* Configuration management
* Secret management

For example, if an application container crashes, Kubernetes can automatically restart or replace it.
