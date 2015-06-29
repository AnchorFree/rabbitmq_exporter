# RabbitMQ Exporter

Prometheus exporter for RabbitMQ metrics, based on RabbitMQ HTTP API.

### Dependencies

* Prometheus [client](https://github.com/prometheus/client_golang) for Golang
* [Logging](https://github.com/Sirupsen/logrus)

[Update]
* [rabbit-hole](https://github.com/michaelklishin/rabbit-hole) HTTP API was removed from the project because of lacking support for HTTPS

### Setting up locally

1. You need **RabbitMQ**. For local setup I recommend this [docker box](https://github.com/mikaelhg/docker-rabbitmq). It's "one-click" solution.

2. For OS-specific **Docker** installation checkout these [instructions](https://docs.docker.com/installation/).

3. Building rabbitmq_exporter:

        $ docker build -t rabbitmq_exporter .

4. Running:

        $ docker run --publish 6060:9672 --rm rabbitmq_exporter

Now your metrics are available through [http://localhost:6060/metrics](http://localhost:6060/metrics).

### Metrics

#### Overview

Total number of:

* channels
* connections
* consumers
* exchanges
* queues

#### Queues

For each queue the number of:

* messages_ready
* messages_unacknowledged
* messages
* messages_ready_ram
* messages_unacknowledged_ram
* messages_ram
* messages_persistent
* message_bytes
* message_bytes_ready
* message_bytes_unacknowledged
* message_bytes_ram
* message_bytes_persistent
* disk_reads
* disk_writes
* consumers
* consumer_utilisation
* memory
