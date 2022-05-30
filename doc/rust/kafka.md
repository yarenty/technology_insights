# Kafka in rust


## rdkafka

https://github.com/fede1024/rust-rdkafka

```toml
rdkafka = "0.28"
```



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





---

# Red Panda

https://redpanda.com/


https://docs.redpanda.com/docs/reference/faq/


```shell
brew install redpanda-data/tap/redpanda && rpk container start
```

```log
Redpanda - The fastest queue in the west!

This installs RPK which, with Docker, enables the running of a local cluster
for testing purposes.

You can start a 3 node cluster locally using the following command:

    rpk container start -n 3

You can then interact with the cluster using commands like the following:

    rpk topic list

When done, you can stop and delete the cluster with the following command:

    rpk container purge

For information on how to setup production evironments, check out our
installation guide here: https://vectorized.io/documentation/setup-guide/
```

Redpanda is a modern streaming platform for mission critical workloads. With Redpanda you can get up and running with streaming quickly and be fully compatible with the Kafka ecosystem.

This quick start guide can help you get started with Redpanda for development and testing purposes. For production or benchmarking, setup a production deployment.

## Get your cluster ready
To get a cluster ready for streaming, either run a single docker container with Redpanda running or a cluster of 3 containers.

```admonish note
You can also use rpk container to run Redpanda in containers without having to interact with Docker at all.
Single command for a 1-node cluster
With a 1-node cluster you can test out a simple implementation of Redpanda.
```

```admonish warning
--overprovisioned is used to accommodate docker resource limitations.
--pull=always makes sure that you are always working with the latest version.
```

```shell
docker run -d --pull=always --name=redpanda-1 --rm \
-p 8081:8081 \
-p 8082:8082 \
-p 9092:9092 \
-p 9644:9644 \
docker.redpanda.com/vectorized/redpanda:latest \
redpanda start \
--overprovisioned \
--smp 1  \
--memory 1G \
--reserve-memory 0M \
--node-id 0 \
--check=false
```

You can do some simple topic actions to do some streaming. Otherwise, just point your Kafka-compatible client to **127.0.0.1:9092**.



```shell
 rpk container start
Downloading latest version of Redpanda
Starting cluster
Waiting for the cluster to be ready...
  NODE ID  ADDRESS
  0        127.0.0.1:50725

Cluster started! You may use rpk to interact with it. E.g:

rpk cluster info --brokers 127.0.0.1:50725

[~] : rpk cluster info --brokers 127.0.0.1:50725
BROKERS
=======
ID    HOST       PORT
0*    127.0.0.1  50725


```




## streaming
Here are some sample commands to produce and consume streams:

Create a topic. We'll call it "twitch_chat":
```shell
docker exec -it redpanda-1 \
rpk topic create twitch_chat --brokers=localhost:9092
```

Produce messages to the topic:
```shell
docker exec -it redpanda-1 \
rpk topic produce twitch_chat --brokers=localhost:9092
```
Type text into the topic and press Ctrl + D to separate between messages.

Press Ctrl + C to exit the produce command.

Consume (or read) the messages in the topic:
```shell
docker exec -it redpanda-1 \
rpk topic consume twitch_chat --brokers=localhost:9092
```

Each message is shown with its metadata, like this:
```json
{
"message": "How do you stream with Redpanda?\n",
"partition": 0,
"offset": 1,
"timestamp": "2021-02-10T15:52:35.251+02:00"
}
```

You've just installed Redpanda and done streaming in a few easy steps.

## Clean Up
When you are finished with the cluster, you can shutdown and delete the containers. Change the commands below accordingly if you used the 1-cluster option, or the 3-cluster option.

```shell
docker stop redpanda-1 redpanda-2 redpanda-3 && \
docker rm redpanda-1 redpanda-2 redpanda-3
```
If you set up volumes and a network, delete them with:

```shell
docker volume rm redpanda1 redpanda2 redpanda3 && \
docker network rm redpandanet
```



