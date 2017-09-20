# Node.js 

## index.js
implemented a simple front-end app used to visualize realtime data
### dependency
socket.io       http://socket.io/

redis           https://www.npmjs.com/package/redis

smoothie        https://www.npmjs.com/package/smoothie

minimist        https://www.npmjs.com/package/minimist

```sh
npm install
```

### running
assuming you have all the services running in a docker-machine called bigdata, and assuming the virtual maching ip is 192.168.99.100
```sh
node index.js --port=3000 --redis_host=192.168.99.100 --redis_port=6379 --subscribe_topic=average-stock-price
```
