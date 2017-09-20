# Redis related code

## redis-producer.py
Redis producer, fetching from Kafka topic then publish to redis PUB
### dependency
kafka-python    https://github.com/dpkp/kafka-python

redis           https://pypi.python.org/pypi/redis

```sh
pip install -r requirements.txt
```

### running
assuming your Kafka redis running in a docker-machine called bigdata and the virtual machine ip is 192.168.99.100
```sh
python redis-publisher.py average-stock-price 192.168.99.100:9092 average-stock-price 192.168.99.100 6379
```


