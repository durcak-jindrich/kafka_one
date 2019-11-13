## Installation and start

1. setup with docker:

```bash
docker-compose up
```

2. create topic from another terminal window:

```bash
docker-compose exec kafka /opt/kafka/bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic helloworld
```

3. check that the topic was created:

```bash
docker-compose exec kafka /opt/kafka/bin/kafka-topics.sh --list --zookeeper zookeeper:2181
```

4. start a command line producer:

```bash
docker-compose exec kafka /opt/kafka/bin/kafka-console-producer.sh --broker-list kafka:9092 --topic helloworld
```

5. open another terminal to use command line consumer:

```bash
docker-compose exec kafka /opt/kafka/bin/kafka-console-consumer.sh --bootstrap-server kafka:9092 --topic helloworld --from-beginning
```

6. to stop the container:

```bash
docker-compose down
```
