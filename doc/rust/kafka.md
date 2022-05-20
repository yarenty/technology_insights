# Kafka in rust


## rdkafka

https://github.com/fede1024/rust-rdkafka


A fully asynchronous, futures-enabled Apache Kafka client library for Rust based on librdkafka.

The library
rust-rdkafka provides a safe Rust interface to librdkafka. The master branch is currently based on librdkafka 1.8.2.


### Benchmark

https://github.com/fede1024/kafka-benchmark





## Librdkafka

https://github.com/edenhill/librdkafka/blob/master/INTRODUCTION.md#broker-version-compatibility





# Kafka



https://docs.rs/kafka/latest/kafka/



https://kafka.apache.org/documentation.html#quickstart



https://kafka.apache.org/31/documentation/streams/quickstart



https://kafka.apache.org/31/documentation/streams/


## Red Panda

https://docs.redpanda.com/docs/reference/faq/






## Kafka usage


```shell
/usr/local/opt/kafka/bin/kafka-topics --create --topic ufos --bootstrap-server localhost:9092

/usr/local/opt/kafka/bin/kafka-topics --describe --topic ufos --bootstrap-server localhost:9092


/usr/local/opt/kafka/bin/kafka-console-producer --topic ufos --bootstrap-server localhost:9092



/usr/local/opt/kafka/bin/kafka-console-consumer --topic ufos --from-beginning --bootstrap-server localhost:9092

```





## Rust examples:

https://github.com/kafka-rust/kafka-rust/blob/master/examples/console-consumer.rs



## Confluence

https://www.confluent.io/blog/crossing-streams-joins-apache-kafka/



