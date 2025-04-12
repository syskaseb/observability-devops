# observability-devops

## How to run the project
* provide .env file with required environment variables
* install docker and docker-compose
* in project's root directory run the following command from terminal
```docker compose up -d```
* go to docker desktop and check the running containers

## Multi-arch images building
### Create multi-arch builder
```
docker buildx create --name multiarch-builder --use
docker buildx inspect --bootstrap
```
### Build and push the image
```
docker buildx build --platform linux/amd64,linux/arm64 \
-t syskaseb/<i.e. observability-discovery-client>:latest \
--push .
```
