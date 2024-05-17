kafka storage - https://kadir-alan.medium.com/apache-kafka-storage-architecture-kafka-streams-series-1-637f310b4bcd

kafka storage - https://rohithsankepally.github.io/Kafka-Storage-Internals/

Kafka setup for local
 
Kafka
========
 
start zookeeper.start bat file like below: Go to C:\kafka, open command prompt here
 
--------------------------------------------------------------------------------------------
 
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
 

start kafka server: go to C:\kafka folder open command prompt
 
---------------------------------------------------------------------------------------
 
.\bin\windows\kafka-server-start.bat .\config\server.properties
 

create a topic
===============
# old version:- .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --topic TestTopic --create --partitions 3 --replication-factor 1
 
.\bin\windows\kafka-topics.bat --create --topic TestTopic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
 
.\bin\windows\kafka-topics.bat --create --topic kafka-prod-topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
 
 
 kafka producer send message to testtopic
=============================================
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic TestTopic1
 

.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic kafka-prod-topic
 
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic product-topic
 

start consumer and get the messages
=====================================
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic TestTopic1 --from-beginning
 
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic kafka-prod-topic --from-beginning
