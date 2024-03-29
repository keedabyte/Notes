# Quick Docker reference

### Checking docker version
```docker
docker --version
```
```docker
docker -v
```

### Checking all docker images present in our system
```docker
docker images
```
```docker
docker image ls
```

### Searching a docker image in docker hub
```docker
docker search <imagename>
```
```docker
docker search redis
```

### Pulling docker image from docker hub
```docker
docker pull <imagename>
```
```docker
docker pull ubuntu
```

### Running a docker image
```docker
docker run <imagename>
```
```docker
docker run --name <custom-container-name> <imagename>
# giving a custom name to container
```

### List all running containers
```docker
docker ps
```

### List all running and stopped containers
```docker
docker ps -a
```
```docker
docker ps --all
```

### Running an image in interactive mode
```docker
docker run -it <imagename/imageid>
```

### Note:  ```docker run``` = ```docker create``` + ```docker start```

### Start and Stop the container
```docker
docker start <containerid>
```
```docker
docker stop <containerid>
```
```docker
docker stop -f <containerid>
# forcefully stop the docker container
```  

### Creating a container of a docker image
```
docker create <imagename/imageid>
```

### Starting the container in attach mode
```docker
docker start -a <container-id>
# -a prints the output of the docker container in our terminal
```  

### Starting the container
```docker
docker start <container-id>
```

### Printing the logs of a container
```docker
docker logs <container-id>
```

### Killing a running container
```docker
docker kill <container-id>
# we need to kill the container if it doesn't stops
```  

### Going inside/Executing a container
```docker
docker exec -it <container-id> <startup-command>
# -i is used for attaching the std in to docker
# -t is used for formatting the output
```  

### Mapping host machine port to docker machine port
```docker
docker run -p 8080:80 nginx
# map docker 80 port to local machine 8080 port
```  

### Running the process in the background
```docker
docker run -d -p 8080:80 nginx
```

### Removing a docker container
```docker
docker rm <container-id>
```

### Removing a docker image
```docker
docker image rm <image-id>
```
```docker
docker rmi <imagename:tagname>
```

### Restarting the container
```docker
docker restart <container-id>
# this command can be used to start the stopped container as well
```  

### Removing all docker stopped container
```docker
docker system prune
```

### inspecting the docker container/images
```docker
docker inspect <container/image id>
```

### Some other useful commands
- docker login  
    use to login into docker hub
- docker commit
- docker push 
- docker copy 
- docker logs 
- docker volume
- docker logout

---
### Creating our own docker image
1. Create a file with name ```Dockerfile```
2. Write the below script in the file
    ```docker
    FROM ubuntu    # base image
	MAINTAINER sanjay   # author name
	RUN apt update  # running the command
	CMD [“echo”, “this is my first ubuntu image”]  # startup command
    ```
3. Build the docker image using terminal.
    ```docker
    docker build -t myubuntuimage .     // use the current directory and create image with the given tag name
    ```

---
## Creating java docker file
- Create a jar file in the current directory
- Write the below script in the file. 
    ```docker
    FROM openjdk
    WORKDIR /usr/src/myapp
    COPY . /usr/src/myapp
    CMD ["java", "-jar", "helloworld".jar"]
    EXPOSE 9595
    ```
- Build the image
- Run the image with below command 
    ```docker
    docker run --name <give-a-name-to-container> -it -p 8000:9595 -d <imagename>
    ```
- Open localhost:8000