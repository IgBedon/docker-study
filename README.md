# Docker Fundamentals
Docker is a powerful tool for developers, as containerization simplifies the development and deployment process.

# Dockerfile
A Dockerfile is a configuration file used to define the image that will later be built and utilized in a container.
This repository includes an example Dockerfile to help you understand its structure and functionality.

# Docker Commands
## Managing Containers
### Show Running Containers
Use -a to display all containers (including stopped ones).
```bash
docker ps
docker ps -a
```

### Run a Container (Create a New Container)
Use -d for detached mode, -it for interactive mode, --name to assign a name to the container, and -p to map ports.
```bash
docker run [options] [imageID or imageName]
# Example: docker run -d -p 8080:80 --name my-container nginx
```

### Stop a Container
```bash
docker stop [containerID]
```

### Start an Existing Container
```bash
docker start [containerID]
```

### Remove a Container
Use -f to force removal.
```bash
docker rm [containerID]
docker rm -f [containerID]
```

## Managing Images
### Show All Images
```bash
docker image ls
```

### Build an Image
Specify the Dockerfile path (default is the current directory).
```bash
docker build [path]
# Example: docker build .
```

### Remove an Image
Use -f to force removal.
```bash
docker image rm [imageID]
docker rmi [imageID]
docker rmi -f [imageID]
```

### Tag an Image
Assign a tag to an image for easier identification.
```bash
docker tag [imageID] [repository:tag]
# Example: docker tag abc123 my-image:1.0
```


## Debugging and Logs
#### Show Logs from a Container
```bash
docker logs [containerID]
```

### Inspect a Container
Get detailed information about a container.
```bash
docker inspect [containerID]
```

### Show System Resource Usage
Monitor resource usage for running containers.
```bash
docker stats
```

## Networking
### List Docker Networks
```bash
docker network ls
```

### Remove Unused Networks
You can use -f to force removal
```bash
docker network prune
docker network prune -f
```

## System Maintenance
### Remove Unused Containers, Networks, and Images
Free up disk space by cleaning unused Docker objects.
```bash
docker system prune
```

### Show Docker System Information
View detailed information about Docker, including containers, images, and resources.
```bash
docker system info
```

## Docker Hub
### Login
Login in Docker Hub
```bash
docker login
```

### Logout
Logout in Docker Hub
```bash
docker logout
```

### Push an Image to a Registry
Send an image to a remote registry like Docker Hub.
```bash
docker push [repository:tag]
# Example: docker push my-image:1.0
```

### Pull an Image from a Registry
Download an image from a remote registry.
```bash
docker pull [repository:tag]
# Example: docker pull nginx:latest
```