# Day 35 – Multi-Stage Builds & Docker Hub

## Task

### Task 1: The Problem with Large Images





### Task 3: Push to Docker Hub

## Run From The Terminal
```text
# Login
docker login

# View local images
docker images

# Tag image
docker tag node-multistage raktimbhuiya/node-multistage:v1

# Push image
docker push raktimbhuiya/node-multistage:v1

# Remove local image
docker rmi raktimbhuiya/node-multistage:v1
docker rmi node-multistage

# Pull from Docker Hub
docker pull raktimbhuiya/node-multistage:v1

# Run the container
docker run -d -p 3000:3000 raktimbhuiya/node-multistage:v1
```