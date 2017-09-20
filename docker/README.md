# Docker environment setup

## code structure

1. local-setup.sh fast deploy single node Kakfa, Cassandra, Zookeeper environment

## MacOS, *nix

1. create a docker-machine virtual machine, 2CPU, 2G memorty
```sh
docker-machine create --driver virtualbox --virtualbox-cpu-count 2 --virtualbox-memory 2048 bigdata
```
2. run script to run all the related docker container (Kafka, Cassandra, Zookeeper)
```sh
./local-setup.sh bigdata
```

## Windows

TODO
