# Docker Fundamentals Guide

## Core Concepts

### Theory
- Docker is used to containerize applications
- Images are templates from which containers are created
- Images can be compared to Classes, while containers are like Objects (instances)
- Docker automatically pulls images from Docker Hub if they don't exist locally

## Essential Commands

### Basic Container Operations
```bash
# Run container in detached mode
docker run -d <image>
```
- Runs image in background regardless of terminal activity

```bash
# Run container with port mapping
docker run -p <Host_Port>:<Container_Port> <image>
```
- Maps system port to container port
- Example: `-p 4000:3000` maps system port 4000 to container port 3000

### Environment Variables
```bash
# Run container with environment variables
docker run -e <ENV_VARIABLE>=<ENV_VALUE> <image>
```

### Container Management
```bash
# List all containers
docker ps -a

# Remove container
docker rm <CONTAINER_ID>

# Remove image
docker rmi <IMAGE>
```

### Interactive Container Access
```bash
# Access container shell
docker exec -it <CONTAINER_ID> <environment>
```
- `-it` enables interactive mode
- Environment can be bash/zsh/shell

## MongoDB Container Example

### Creating MongoDB Container
```bash
docker run -d \
    --name mymongo \
    -p 3501:27017 \
    -e MONGO_INITDB_ROOT_USERNAME=pavan \
    -e MONGO_INITDB_ROOT_PASSWORD=mypsswd \
    mongo
```

### Connection Details
- System Port: 3501
- MongoDB Port: 27017
- Connection String: `mongodb://pavan:mypsswd@localhost:27017`
