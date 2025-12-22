# Docker Cheat Sheet

## Images
```
docker pull <image>                    " pulls an image from Docker Hub
docker images                          " shows images
docker rmi <img_id> or <img_name:tag>  " deletes an image
```

## Containers
```
run flags: --network none              " inits a container with no network connection)
           --network <name>            " inits in a network
           --name <name>               " gives a container a name 
           -it and /bin/sh at the end  " starts a shell session within the container 
docker run -d -e NODE_ENV=development -e url=http://localhost:3001 -p 3001:2368 -v <volume>:/var/lib/<image> <image>
" spins up a container, -d runs it in detached mode, -e NODE_ENV=development sets an environment variable within the container, this tells the image to run in dev mode rather than prod for example, -e url=http://localhost:3001 sets another environment variable, this one tells the image that we want to be able to access the app via a URL on our host machine.
-p to map the ports, -v <volume>:/var/lib/<app> mounts the <volume> to that path in the container

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
```
## Network
```
docker network create <name>           " creates a new network
docker network ls                      " lists current networks

```


