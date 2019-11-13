## Installation and start

1. start Kafka and Zookeeperwith docker:
```bash
cd docker
docker-compose up
```
2. create two topics (user and global) 
```bash
docker-compose exec kafka /opt/kafka/bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic user-events
docker-compose exec kafka /opt/kafka/bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic global-events
```

Topics can be listed with the following command:
```bash
docker-compose exec kafka /opt/kafka/bin/kafka-topics.sh --list --zookeeper zookeeper:2181
```
3. Build and run Producer (sends 100 000 messages to Kafka) 
```bash
cd producer
mvn clean package
target/producer
```
4. Build and run Consumer 
```bash
cd consumer
mvn clean package
target/consumer
```
