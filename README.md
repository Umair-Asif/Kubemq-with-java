# Kubemq-with-java

Steps to follow:

Install Docker Engine according to your Operating System (https://docs.docker.com/engine/install).
After installing and meeting all the requirements and prerequisites

## Run this command on terminal/cmd to verify if docker is installed successfully
- docker --version

## Run this command to verify if any docker image is up
- docker ps

## Or

- docker ls -a

## If image exists you'll get something like this
5cc9ae##f4ba        kubemq/kubemq       "./kubemq-run"      1 hours ago        Up 24 hours         0.0.0.0:8181->8080/tcp, 0.0.0.0:9191->9090/tcp, 0.0.0.0:51000->51000/tcp   determined_banach

>by default Sender(publisher) port is **8080**, Receiver (subscribers/listeners) port is **9090** and cluster port is **50000**

## To start using kubemq message queue, we first need to run a kubemq docker container

- docker run -d -p 8181:8080 -p 52000:50000 -p 9191:9090 -v $PWD:/store -e KUBEMQ_TOKEN=927deb10-c0d0-4d0e-9bcf-8aa4809aa076 kubemq/kubemq

 
 ### In order to run change cluster port "In our case it is 52000" you'll need to set cluster port in /src/main/resources/application.yaml
 - kubemq.address: localhost:52000
 
>(https://piotrminkowski.com/2020/01/17/kubernetes-messaging-with-java-and-kubemq/)
