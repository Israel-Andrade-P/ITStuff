# Docker Cheat Sheet

## Images
```
docker pull <image>                    " pulls an image from Docker Hub
docker images                          " shows images
docker rmi <img_id> or <img_name:tag>  " deletes an image
docker build <dockerfile_path> -t <img_name>:<version> " build custom images
```

## Containers
```
run flags: -d                          " detached mode  
           -e                          " adds a env variable 
           -p                          " maps ports  
           -v                          " mounts a volume 
           --network none              " inits a container with no network connection)
           --network <name>            " inits in a network
           --name <name>               " gives a container a name 
           -it and /bin/sh at the end  " starts a shell session within the container 
           --memory                    " limit the memory available to the container
           --cpus                      " limit the cpus shares available to the container  
Ex: docker run -d -e NODE_ENV=development -e url=http://localhost:3001 -p 3001:2368 -v <volume>:/var/lib/<image> <image>
Ex: docker run -d --cpus="0.25" --name cpu-stress alexeiled/stress-ng --cpu 2 --timeout 10m
docker run sh -c <sh_script>           " runs a script in a container
docker ps (flags: -a)                  " shows containers
docker stop <container_id>             " stops container
docker stop $(docker ps -q)            " lists running containers IDs and stops them all at once 
docker rm <container_id>               " removes container 
docker container prune                 " removes all stopped containers 
```

## Volumes
```
docker volume create <volume>          " creates a volume
docker volume ls                       " shows volumes
docker volume inspect <volume>         " inspect volume    
docker volume rm <volume>              " removes a volume
docker volume prune                    " deletes unused volumes 
```
## Management
```
docker exec <container_id> <command>   " executes commands in a container, might be useful for debugging
docker exec -it <container_id> /bin/sh " starts a shell session inside the container
docker logs [OPTIONS] <container>      " show container logs
logs flags: -f                         "follows the logs in realtime
            --tail <number>            " shows the <number> most recent logs 
docker stats                           " shows resource usage for a container
docker top <container>                 " shows running processes in a container  
```
## Network
```
docker network create <name>           " creates a new network
docker network ls                      " lists current networks

```


