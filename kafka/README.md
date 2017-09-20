# Kafka related code

## simple-data-producer.py
implemented a kafka producer,fetching one piece of stock information from Google finance, send to Kafka

### dependency
googlefinance   https://pypi.python.org/pypi/googlefinance

kafka-python    https://github.com/dpkp/kafka-python

schedule        https://pypi.python.org/pypi/schedule

```sh
pip install -r requirements.txt
```

### running
assuming a Kafka running in a docker-machine called bigdata and virtual machine ip is 192.168.99.100
```sh
python simple-data-producer.py AAPL stock-analyzer 192.168.99.100:9092
```
