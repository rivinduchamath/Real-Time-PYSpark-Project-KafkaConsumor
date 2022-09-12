pip install scikit-learn

Apache Kafka :

bin/kafka-server-start.sh config/server.properties

bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning


./kafka-topics.sh --create --topic orderstopic --bootstrap-server localhost:9092

bin/kafka-topics.sh --list --bootstrap-server localhost:9092 all topics

bin/kafka-topics.sh --create --topic test-topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 4
create Topic :
kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic orderstopic 

delete topic IF WANT:
kafka-topics.sh --zookeeper localhost:2181 --delete --topic orderstopic
bin/kafka-topics.sh  --delete --topic orderstopic  --bootstrap-server localhost:9092 

retrieve list of topics in kafka
kafka-topics.sh --list --zookeeper localhost:2181

locking msg in topic and consume 
kafka-console-consumer-sh --bootstrap-server localhost:9092 --topic orderstopic

2nd Part
MY SQL

mysql -u root -h localhost -p

show databases;

create database sales_db;
use sales_db;

create table total_sales_by_source_state
(
 source varchar(255)  null ,
state varchar(255) null,
    total_sum_amount double null,
    processed_at  datetime  null,
batch_id  int(11)  null
);

-----------------------------------
Apache Cassandra:

cqlsh --cqlversion=3.4.4

CREATE KEYSPACE sales_ks WITH replication = {'class' : 'SimpleStrategy', 'replication_factor' : 1 };

use sales_ks;


get Databases On Cassandra:
describe keyspaces;

use sales_ks;
describe tables;

select * from order_tbl;

drop table order_tbl;

CREATE TABLE sales_ks.order_tbl
(
    order_id  int PRIMARY KEY ,
    created_at  text,
    discount text,
    product_id text,
    quantity text,
    subtotal text,
    tax text,
    total text,
     int,
    timestamp text
);














