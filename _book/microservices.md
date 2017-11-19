##### MetadataService

```docker build -t "vertx/metadataapi" ./```
```docker run -p 8090:8090 vertx/accountsapi```
```docker run -p 8190:8190 vertx/metadataapi```
```docker run -p 5701:5701 vertx/clustermanager```

``java -Dvertx.hazelcast.config=./src/conf/cluster.xml -jar target/metadata-service-fat.jar -cluster```

docker rmi $(docker images | grep "<none>" | awk "{print \$3}")


-Dvertx.hazelcast.config=cluster.xml
