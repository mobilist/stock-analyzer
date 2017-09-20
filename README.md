# A full-stack real-time stock analyzer web application

Techniques used: Apache Zookeeper, Apache Cassandra, Apache Kakfa, Apache Mesos, Redis, Docker, NodeJS

## Introduction

This is a complete big data platform to process stock data in real time at 2TB/day(upperlimit). What is does is firstly grabing the data from google finance 1 message/s. Each record has a last trading time, last trading price, last trading currency and stock symbol for example. I chose Apache kafka which working as a high performance messaging system, whose benchmark could reach 200 thousands messages per second. If you count the message and the size of the data is about 2Tb per day(upperlimit). To store the data, in my use case I choose Apache cassandra which is a highly scalable peer to peer data storage system without single point failure. Thirdly I chose apache spark, I applied spark streaming API to write a simple algorithm to process data in real time. Then comes to the data visualizatin part. I developed a simple web app using redis, NodeJS, and socket.io, which renders the process result to the web UI. So you can see the price change in the UI in real time. Lastly, for all the code in my project I packaged them in the docker container and deployed them using Apache Mesos to achieve highly scalable deployment.


## How to deploy and run on your local computer

1. Go to folder Docker to set up the environment 
2. Follow instructions in seperate foders including Redis Cassandra Kafka Spark to add required dependencies
3. Start the virtual machine named as "bigdata" you created in step1 
4. Run the .py following the instructions in the accordingly folder
      4.1 kafka/simple.producer.py consume data
      4.2 cassandra/data.storage.py  store data
      4.3 spark/stream-processing.py fetch and process data from kafka then write it back
      4.4 redis/redis-publisher.py work as message queue between kakfa and sprak, publish processed data
      4.5 nodejs/index.js start the website server to visualize the data
      4.6 type in localhost:3000 in web browser
