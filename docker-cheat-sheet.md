#Docker Commands Cheat Sheet 

$ docker --version 

$ docker --help

####Pull an image from docker hub 
$ docker pull <image>   

####List running containers 
$ docker ps 
$ docker ps -a 

####Create a container 
$ docker run --name <container> <image>   
 
####Create a container to run it as a daemon(in background)
$ docker run -dt --name <container> <image>    

####Interact with the container, run cmds inside a container 
$ docker exec -it <container> bash

####Run a container and publishing a port 
$ docker run -td -p <host_port>:<container_port> <image> 

####Run a container interactively and remove after exiting
$ docker container run --rm -it <image> 


$ docker start <container>
$ docker stop <container>
$ docker rm <container>


####Create an image(custom image) from the container 
$ docker commit <container_hash> <img_name>:<version>


####Copy Files from container to local machine 
$ docker cp <container_hash>:<file> . 


####Copy Files to container from local machine 
$ docker cp <file> <container_hash>:~/

####Remove running container
$ docker rm -f <container>   
$ docker stats 

####List of docker image
$ docker image ls 

####Removes image 
$ docker image rm <image_hash> 


####List of network images 
$ docker network ls     


####Create a new network 
$ docker network create <networkname>     

####Create a new container with a specified network 
$ docker run -itd --rm --network <network> --name <container> <image>    
