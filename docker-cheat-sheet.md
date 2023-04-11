#          Docker Commands Cheat Sheet 

$ docker --version 

$ docker --help

# Pull an image from docker hub 
$ docker pull <image>   

# List running containers 
$ docker ps 
$ docker ps -a 

# Create a container 
$ docker run --name <container> <image>   
 
# Create a container to run it as a daemon(in background)
$ docker run -dt --name <container> <image>    

# Interact with the container, run cmds inside a container 
$ docker exec -it <container> bash

# Run a container and publishing a port 
$ docker run -td -p <host_port>:<container_port> <image> 

# Run a container interactively and remove after exiting
$ docker container run --rm -it <image> 

$ docker start <container>
$ docker stop <container>
$ docker rm <container>
$ docker rm -f <container>   -> remove running container

$ docker stats 

$ docker image ls    -> list of docker images 

$ docker network ls     -> list of network images 

$ docker network create <networkname>      -> create a new network 
$ docker run -itd --rm --network <network> --name <container> <image>    -> create a new container with a specified network 
