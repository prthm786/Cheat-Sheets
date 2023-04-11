#          Docker Commands Cheat Sheet 

$ docker --version 
$ docker --help

$ docker pull <image>   -> pull an image from docker hub 

$ docker ps  -> list running containers 
$ docker ps -a 

$ docker run --name <container> <image>   -> create a container 
$ docker run -dt --name <container> <image>  -> create a container to run it as a daemon(in background)  
$ docker exec -it <container> bash  -> interact with the container, run cmds inside a container 

$ docker run -td -p <host_port>:<container_port> 
<image> 

$ docker container run --rm -it <image>.  -> run a container interactively and remove after exiting 

$ docker start <container>
$ docker stop <container>
$ docker rm <container>
$ docker rm -f <container>   -> remove running container

$ docker stats 

$ docker image ls    -> list of docker images 

$ docker network ls     -> list of network images 

$ docker network create <networkname>      -> create a new network 
$ docker run -itd --rm --network <network> --name <container> <image>    -> create a new container with a specified network 
