# Lesson 07: Real-Time Data — Spark Streaming + Kafka

**Estimated time:** 8-10 hours
**Week(s):** 9

## Learning Objectives

- [ ] Understand event streaming concepts (events, topics, partitions)
- [ ] Set up a local Kafka cluster
- [ ] Write Kafka producers and consumers in Python
- [ ] Use Spark Structured Streaming to process Kafka data
- [ ] Implement watermarking and late-arriving data handling
- [ ] Use Apache Flink basics (alternative to Spark Streaming)
- [ ] Compare streaming patterns: at-most-once, at-least-once, exactly-once
- [ ] Build a real-time pipeline end-to-end

---

## Video Resources

> **See [VIDEO-RESOURCES-VERIFIED.md](../VIDEO-RESOURCES-VERIFIED.md) for the canonical list.**

### Apache Kafka

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Confluent: Apache Kafka 101 (official, free) | ~2 hrs | [developer.confluent.io](https://developer.confluent.io/learn-kafka/apache-kafka/events/) |
| 🎥 Confluent Developer (all free courses) | varies | [developer.confluent.io/courses](https://developer.confluent.io/courses/) |
| 🎥 Confluent: Send Your First Event with Kafka (hands-on) | ~30 min | [developer.confluent.io](https://developer.confluent.io/courses/apache-kafka/get-started-hands-on/) |
| 🎥 Confluent: Kafka Streams 101 | 2.5 hrs | [developer.confluent.io](https://developer.confluent.io/courses/kafka-streams/) |
| 🎥 TechWorld with Nana — Apache Kafka Complete Course for Beginners | varies | [Class Central](https://www.classcentral.com/course/youtube-apache-kafka-complete-course-for-beginners-487303) |
| 🎥 TechWorld with Nana — Kafka Tutorial for Beginners | ~1 hr | [Class Central](https://www.classcentral.com/course/youtube-kafka-tutorial-for-beginners-everything-you-need-to-get-started-431676) |
| 🔗 Confluent Learn Kafka Courses (companion repo) | — | [github.com/confluentinc/learn-kafka-courses](https://github.com/confluentinc/learn-kafka-courses) |

### Spark Structured Streaming

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Databricks official YouTube — streaming content | varies | [@Databricks](https://www.youtube.com/@Databricks) |
| 📚 Structured Streaming Programming Guide | — | [spark.apache.org](https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html) |

### Apache Flink

| Resource | Duration | Link |
|----------|----------|------|
| 🎥 Apache Flink official YouTube | varies | [@ApacheFlink](https://www.youtube.com/@ApacheFlink) |
| 🎥 Confluent Developer (Flink courses) | varies | [developer.confluent.io/courses](https://developer.confluent.io/courses/) |
| 📚 Flink Documentation | — | [flink.apache.org](https://flink.apache.org/) |

### Percipio (Skillsoft) Alternatives

| Course | Topic |
|--------|-------|
| 🎓 "Apache Kafka: Stream Processing" | Kafka fundamentals |
| 🎓 "Real-Time Data Processing" | Streaming concepts |
| 🎓 "Spark Structured Streaming" | Spark for streaming |

---

## Hands-On Assignments

### Assignment 1: Local Kafka Setup (1.5 hrs)
- [ ] Run Kafka locally with Docker Compose (Confluent or Bitnami images)
- [ ] Create a topic
- [ ] Send messages with `kafka-console-producer`
- [ ] Read messages with `kafka-console-consumer`
- [ ] Inspect partitions and offsets

```yaml
# docker-compose.yml snippet
services:
  kafka:
    image: confluentinc/cp-kafka:latest
    environment:
      KAFKA_NODE_ID: 1
      KAFKA_PROCESS_ROLES: broker,controller
      KAFKA_LISTENERS: PLAINTEXT://kafka:9092,CONTROLLER://kafka:9093
      KAFKA_CONTROLLER_QUORUM_VOTERS: 1@kafka:9093
    ports:
      - "9092:9092"
```

### Assignment 2: Python Producer/Consumer (2 hrs)
- [ ] Use `kafka-python` or `confluent-kafka-python`
- [ ] Build a producer that simulates IoT sensor events (every second)
- [ ] Build a consumer that reads and prints events
- [ ] Add JSON serialization
- [ ] Try multiple consumers in a consumer group (load balancing)

```python
from kafka import KafkaProducer, KafkaConsumer
import json, time, random

producer = KafkaProducer(
    bootstrap_servers='localhost:9092',
    value_serializer=lambda v: json.dumps(v).encode('utf-8')
)

while True:
    event = {
        'sensor_id': f'sensor_{random.randint(1, 100)}',
        'temperature': random.uniform(20, 30),
        'timestamp': time.time()
    }
    producer.send('iot-events', event)
    time.sleep(1)
```

### Assignment 3: Spark Structured Streaming + Kafka (3 hrs)
- [ ] Read from Kafka using Spark Structured Streaming
- [ ] Apply transformations (filter, parse JSON, aggregate)
- [ ] Write output to console for debugging
- [ ] Write output to Delta table (in Databricks Community Edition)
- [ ] Add a tumbling window aggregation (5-minute averages)
- [ ] Add a watermark for late data

```python
from pyspark.sql.functions import from_json, col, window, avg
from pyspark.sql.types import StructType, StringType, DoubleType, TimestampType

schema = (StructType()
    .add("sensor_id", StringType())
    .add("temperature", DoubleType())
    .add("timestamp", TimestampType())
)

df = (spark.readStream
    .format("kafka")
    .option("kafka.bootstrap.servers", "localhost:9092")
    .option("subscribe", "iot-events")
    .load()
    .selectExpr("CAST(value AS STRING) as json_str")
    .select(from_json(col("json_str"), schema).alias("data"))
    .select("data.*")
)

agg = (df
    .withWatermark("timestamp", "10 minutes")
    .groupBy(window(col("timestamp"), "5 minutes"), col("sensor_id"))
    .agg(avg("temperature").alias("avg_temp"))
)

query = (agg.writeStream
    .outputMode("append")
    .format("console")
    .start()
)
query.awaitTermination()
```

### Assignment 4: Streaming Patterns (1.5 hrs)
- [ ] Implement an event-time vs. processing-time comparison
- [ ] Add late-data handling with watermarks
- [ ] Test exactly-once semantics with checkpointing
- [ ] Read about Kafka transactions

### Assignment 5: Optional — Apache Flink (1.5 hrs)
- [ ] Run Flink locally
- [ ] Write a basic Flink job (Java or Python via PyFlink)
- [ ] Compare developer experience to Spark Streaming
- [ ] Note: Zach Wilson's bootcamps have started featuring Flink more heavily — worth knowing the basics

---

## Key Concepts to Master

1. **Event Streaming** — Events vs. messages, immutability, replay
2. **Topics & Partitions** — Parallelism unit in Kafka
3. **Consumer Groups** — Load balancing
4. **Offsets** — Position tracking, exactly-once
5. **Watermarks** — Late data handling
6. **Tumbling vs. Sliding Windows** — Window types
7. **Stateful Operations** — Joins, aggregations across micro-batches
8. **Backpressure** — Handling slow consumers
9. **Schema Registry** — Schema evolution for events (Avro, Protobuf)
10. **At-most-once / At-least-once / Exactly-once** — Delivery semantics

---

## Recommended Reading

- 📚 [Kafka: The Definitive Guide (free PDF from Confluent)](https://www.confluent.io/resources/kafka-the-definitive-guide/)
- 📚 [Designing Data-Intensive Applications](https://dataintensive.net/) — Chapters on streaming
- 📚 [Spark Structured Streaming Programming Guide](https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html)
- 📚 [Confluent Developer](https://developer.confluent.io/) — Free courses and tutorials

---

## Cost-Saving Setup

- **Kafka:** Run locally with Docker (zero cost) or Confluent Cloud free tier ($400 credits)
- **Spark Streaming:** Databricks Community Edition is free for streaming
- **Flink:** Run locally with Docker

---

## Progress Tracker

- [ ] Watched Kafka videos (3+ hrs)
- [ ] Watched Spark Streaming videos (2+ hrs)
- [ ] Completed Assignment 1 (Kafka setup)
- [ ] Completed Assignment 2 (producer/consumer)
- [ ] Completed Assignment 3 (Spark + Kafka pipeline)
- [ ] Completed Assignment 4 (streaming patterns)
- [ ] (Optional) Completed Assignment 5 (Flink intro)
- [ ] Can explain delivery semantics
- [ ] Can implement watermarking and windowing
- [ ] Can debug a streaming job from logs/UI
