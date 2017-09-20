# Cassandra related code

## data-storage.py
Implemented Cassandra data store and get process

### dependency
cassandra-driver    https://github.com/datastax/python-driver

cql

```sh
pip install -r requirements.txt
```

### running
assuming you are running Cassandra in a docker-machine called bigdata and the virtual ip is 192.168.99.100

use cqlsh client to create a keyspace and table
```sh
CREATE KEYSPACE "stock" WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1} AND durable_writes = 'true';
USE stock;
CREATE TABLE stock (stock_symbol text, trade_time timestamp, trade_price float, PRIMARY KEY (stock_symbol,trade_time));
```

```sh
python data-storage.py stock-analyzer 192.168.99.100:9092 stock stock 192.168.99.100
```
