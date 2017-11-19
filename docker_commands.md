### docker

 ```docker ps``` list docker process running  
 ``` docker pull nginx``` pull down docker image. The image will be pulled from docker global repo.  

```docker images``` list the docker images

```docker run -d -p 9080:80 --name webserver nginx``` run a docker image in the container.  
_-d_ for detached process  
_--name_ name of the process. one the image is tagged with a name we can use the name to start/stop container.  
```docker start webserver```  
```docker build -t <namespace\imagename>``` to build a docker image using the DockerFile  

```docker save imagename | minikube ssh docker load```
 to push a localdocker image to minikube docker registry.

 ```docker exec -it my_debian bash```
 run a command in the container.

#### running a maven project and uploading the docker image to local registry

dockerfile plugin spotify

```mvn clean install dockerfile:build```
```docker push localhost:5000/my-spring-boot-docker```
```docker image remove localhost:5000/my-spring-boot-docker```
```docker pull localhost:5000/my-spring-boot-docker```
