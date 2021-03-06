# InfluxDB


http://localhost:8086/

https://docs.influxdata.com/influxdb/v2.0/get-started/


## Installation


Or, if you don't want/need a background service you can just run:


```bash
INFLUXD_CONFIG_PATH=/usr/local/etc/influxdb2/config.yml influxd
```

Output:

```txt
==> Summary
🍺  /usr/local/Cellar/influxdb/2.0.7: 9 files, 215.5MB
[/u/l/C/h/3/sbin] : influxd
2021-06-17T12:00:11.995404Z	info	Welcome to InfluxDB	{"log_id": "0UnTKprl000", "version": "2.0.7", "commit": "none", "build_date": "2021-06-17T12:00:02Z"}
2021-06-17T12:00:12.075841Z	info	Resources opened	{"log_id": "0UnTKprl000", "service": "bolt", "path": "/Users/yarenty/.influxdbv2/influxd.bolt"}
2021-06-17T12:00:12.115563Z	info	Bringing up metadata migrations	{"log_id": "0UnTKprl000", "service": "migrations", "migration_count": 15}
2021-06-17T12:00:15.710516Z	info	Using data dir	{"log_id": "0UnTKprl000", "service": "storage-engine", "service": "store", "path": "/Users/yarenty/.influxdbv2/engine/data"}
2021-06-17T12:00:15.710996Z	info	Compaction settings	{"log_id": "0UnTKprl000", "service": "storage-engine", "service": "store", "max_concurrent_compactions": 8, "throughput_bytes_per_second": 50331648, "throughput_bytes_per_second_burst": 50331648}
2021-06-17T12:00:15.711019Z	info	Open store (start)	{"log_id": "0UnTKprl000", "service": "storage-engine", "service": "store", "op_name": "tsdb_open", "op_event": "start"}
2021-06-17T12:00:15.711170Z	info	Open store (end)	{"log_id": "0UnTKprl000", "service": "storage-engine", "service": "store", "op_name": "tsdb_open", "op_event": "end", "op_elapsed": "0.153ms"}
2021-06-17T12:00:15.711209Z	info	Starting retention policy enforcement service	{"log_id": "0UnTKprl000", "service": "retention", "check_interval": "30m"}
2021-06-17T12:00:15.711230Z	info	Starting precreation service	{"log_id": "0UnTKprl000", "service": "shard-precreation", "check_interval": "10m", "advance_period": "30m"}
2021-06-17T12:00:15.711308Z	info	Starting query controller	{"log_id": "0UnTKprl000", "service": "storage-reads", "concurrency_quota": 1024, "initial_memory_bytes_quota_per_query": 9223372036854775807, "memory_bytes_quota_per_query": 9223372036854775807, "max_memory_bytes": 0, "queue_size": 1024}
2021-06-17T12:00:15.713368Z	info	Configuring InfluxQL statement executor (zeros indicate unlimited).	{"log_id": "0UnTKprl000", "max_select_point": 0, "max_select_series": 0, "max_select_buckets": 0}
2021-06-17T12:00:16.133851Z	info	Listening	{"log_id": "0UnTKprl000", "service": "tcp-listener", "transport": "http", "addr": ":8086", "port": 8086}
2021-06-17T12:00:16.133862Z	info	Starting	{"log_id": "0UnTKprl000", "service": "telemetry", "interval": "8h"}

2021-06-17T12:00:29.400528Z	info	Stopping	{"log_id": "0UnTKprl000", "service": "telemetry", "interval": "8h"}
2021-06-17T12:00:29.400522Z	info	Terminating precreation service	{"log_id": "0UnTKprl000", "service": "shard-precreation"}
2021-06-17T12:00:29.400574Z	info	Stopping	{"log_id": "0UnTKprl000", "service": "scraper"}
2021-06-17T12:00:29.400695Z	info	Stopping	{"log_id": "0UnTKprl000", "service": "tcp-listener"}
2021-06-17T12:00:29.402012Z	info	Stopping	{"log_id": "0UnTKprl000", "service": "task"}
2021-06-17T12:00:29.402220Z	info	Stopping	{"log_id": "0UnTKprl000", "service": "nats"}
2021-06-17T12:00:29.402605Z	info	Stopping	{"log_id": "0UnTKprl000", "service": "bolt"}
2021-06-17T12:00:29.402683Z	info	Stopping	{"log_id": "0UnTKprl000", "service": "query"}
2021-06-17T12:00:29.404128Z	info	Stopping	{"log_id": "0UnTKprl000", "service": "storage-engine"}
2021-06-17T12:00:29.404183Z	info	Closing retention policy enforcement service	{"log_id": "0UnTKprl000", "service": "retention"}
[/u/l/C/h/3/sbin] :
[/u/l/C/h/3/sbin] :
[/u/l/C/h/3/sbin] : brew services start influxdb
==> Successfully started `influxdb` (label: homebrew.mxcl.influxdb)
```


## Setup



1. Set up InfluxDB through the UI with InfluxDB running, visit localhost:8086.
2. Click Get Started
3. Set up your initial user - yarenty
4. Enter a Username for your initial user. - q1t5
5. Enter a Password and Confirm Password for your user.
6. Enter your initial Organization Name. com.yarenty.metrics
7. Enter your initial Bucket Name. - metrics
8. Click Continue.

InfluxDB is now initialized with a primary user, organization, and bucket. 

You are ready to write or collect data.


```bash
To restart influxdb after an upgrade:
  brew services restart influxdb
Or, if you don't want/need a background service you can just run:
  /usr/local/opt/influxdb/bin/influxd
```












