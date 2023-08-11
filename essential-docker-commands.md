# Essential Docker Commands

## Image Management

### Pull an Image from Docker Hub
```bash
docker pull image_name:tag
```
### List Downloaded Images
```bash
docker images
```
### Remove an Image
```sh
docker rmi image_name:tag
```
## Container Lifecycle

### Create a Container
```sh
docker run --name -d container_name image_name:tag
```
- **--name** -> give name to container
- **-d**  -> detach mode. Container will run in background.
### Container with Port Mapping
```bash
docker run -d -p 3000:5173 --name rc1 react-image
```
- **-p** -> Map port `3000` of host machine to `5173` port exposed by the docker container 
### Start a Container
```bash
docker start container_name
```
### Stop a Running Container
```bash
docker stop container_name
```
### Restart a Container
```bash
docker restart container_name
```
### Remove a Stopped Container
```sh
docker rm container_name
```
## Container Management
### List Running Containers

```bash
docker ps
```
### List All Containers (Including Stopped)

```bash
docker ps -a
```

### View Logs of a Container
```bash
docker logs container_name
```
### Access a Shell Inside a Container
```bash
docker exec -it container_name /bin/sh
```
- **it** -> runs the Docker image in interactive mode (keep Standard Input Stream)
- **/bin/bash** -> shell inside the container


## Networking

### List Docker Networks
```bash
docker network ls
```
### Create a Docker Network
```bash
docker network create new_name # new bridge netwok will be created
```

### Container with New Network
```bash
docker run -d --network=new_name --name secure image_name
```
## Volume Management
### Create a Volume
```bash
docker volume create volume_name
```
### List Volumes
```bash
`docker volume ls
```
### Attach a Volume to a Container
```bash
# docker run -v dirLocalDirectory:dirContainerDirectory -d -p 3000:5173 --name rc1 react-image
docker run -v $(pwd):/app/ -d -p 3000:5173 --name rc1 react-image
```

## Docker Compose (for Multi-Container Applications)
### Start Containers Defined in a Compose File

```bash
docker-compose up
```

### Stop and Remove Containers Defined in a Compose File
```bash
docker-compose down
```

### Rebuild Images each time
```bash
docker-compose up --build
```
## Cleanup
### Remove All Stopped Containers

```bash
docker container prune
```
### Remove All Unused Images
```bash
docker image prune
```
