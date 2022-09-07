pip install scikit-learn

Apache Kafka :

create Topic :
kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic orderstopic 

delete topic IF WANT:
kafka-topics.sh --zookeeper localhost:2181 --delete --topic orderstopic 

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
    batch_id  int(11)  null ,
    processed_at  datetime(50)  null,
    total_sum_amount double null,
    state varchar(255) null,
    source varchar(255)  null
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
    tax text;
    total text,
    customer_id int,
    timestamp text
);














