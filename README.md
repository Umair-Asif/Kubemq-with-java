# Kubemq-with-java

Steps to follow:

Install Docker Engine according to your Operating System (https://docs.docker.com/engine/install).
After installing and meeting all the requirements and prerequisites

## run this command on terminal/cmd to verify if docker is installed successfully
- docker --version

## run this command to verify if any docker image is up
- docker ps

## or

- docker ls -a

## if image exists you'll get something like this
5cc9ae##f4ba        kubemq/kubemq       "./kubemq-run"      1 hours ago        Up 24 hours         0.0.0.0:8181->8080/tcp, 0.0.0.0:9191->9090/tcp, 0.0.0.0:51000->51000/tcp   determined_banach

## To start using kubemq message queue, we first need to run a kubemq docker container

- docker run -d -p 8181:8080 -p 52000:50000 -p 9191:9090 -v $PWD:/store -e KUBEMQ_TOKEN=927deb10-c0d0-4d0e-9bcf-8aa4809aa076 kubemq/kubemq

 
 
