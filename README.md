## run multiple mongodb version on single host
```
docker run --name mongo-4 -d mongo:4
docker run --name mongo-5 -d mongo:5
```

## show active container
```
docker ps 
```

## get resource usage
```
docker stats
```

## get list of image
```
docker image
```

## get latest image
```
docker run --name mongo -d mongo
```

## pull docker image 
```
docker pull redis
```

## docker container command
```
docker stop <container name>
docker start <container name>
docker restart <container name>
docker rm -f <container name>
```

## get pod active and deactivate container
```
docker ps -a
```

## docker build image
```
docker build -t <tag name> .
```

## docker expose port
```
docker run -p 8000:8000 <image>

# docker run -d -p 8000:8000 --name php myphp
```

## docker container command 
```
docker exec -it <container name> bash
docker attach <container name>
docker logs <container name>
```

## docker network
```
docker network ls
```

## docker create network
```
docker network create mongo
```

## create mongo and mongo express service
```
docker run --name mongo --network mongo -d \
    -e MONGO_INITDB_ROOT_USERNAME="root" \
    -e MONGO_INITDB_ROOT_PASSWORD="root" \
    mongo
    
docker run -d \
    --network mongo \
    --name mongo-express \
    -p 8081:8081 \
    -e ME_CONFIG_MONGODB_SERVER="mongo" \
    -e ME_CONFIG_MONGODB_ADMINUSERNAME="root" \
    -e ME_CONFIG_MONGODB_ADMINPASSWORD="root" \
    -e ME_CONFIG_BASICAUTH_USERNAME="admin" \
    -e ME_CONFIG_BASICAUTH_PASSWORD="admin" \
    mongo-express
```

## delete mongodb server
```
docker rm -f mongo
```

## docker persist data mongodb
```
docker run --name mongo --network mongo -d \
    -v $(pwd)/mongostorage:/data/db \
    -e MONGO_INITDB_ROOT_USERNAME="root" \
    -e MONGO_INITDB_ROOT_PASSWORD="root" \
    mongo
```

## docker container debug command 
```
docker exec -it <container name> bash
docker attach <container name>
docker logs <container name>
```


