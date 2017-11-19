## commands to work with kubernetes
```minikube version```

```minikube start``` - start the minikube in a vm

```minikube ssh docker images``` - images availabe for kubernetes

```minikube start``` - start the minikube in a vm  

```eval $(minikube docker-env)``` - to build and push docker images to kubenetes docker registry  
```eval $(minikube docker-env -u)``` - get back to local docker registry.  


This below is a sample spring boot application.
```kubectl run kubernetes-springboot --image=springio/gs-spring-boot-docker:latest --port=8080```
```kubectl get deployments,pods,services,ing``` - show all resources deployed.  
```kubectl get deployments```  
```kubectl delete deployment <deploymentid>```  
```kubectl get pods```  
```kubectl delete pod <podid>```  
```kubectl get services```  
```kubectl run kubernetes-myspringboot --image=localhost:5000/my-spring-boot-docker:latest --port=8080```  

 ```minikube dashboard``` opens the kubernetes cluster in the browser. Grab the ip of the cluster ip which is exposed and use the port from the kubectl get services
example  

Run a docker registry inside kubenetes  
```kubectl run -d -p 5000:5000 --name registry registry:2```  
```kubectl run registry --image=registry:2 --port=5000```  


```minikube service metadata-service --url``` - will provide the service endpoint url.
```kubectl create -f api-gateway-deployment.yaml```  

Add minikube ingress
```minikube addons enable ingress```

 ```  
    internet
        |
  ------------
  [ Services ]
```

An Ingress is a collection of rules that allow inbound connections to reach the cluster services.

```
    internet
        |
  [ Ingress ]
   --|-----|--
  [ Services ]
```
