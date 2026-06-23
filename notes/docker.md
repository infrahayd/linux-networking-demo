# Images
docker images
- list downloaded images

docker pull [image name]
- download an image from docker hub

docker rmi [image name]
- remove an image

docker build -t [name] .
- -t tags the image with a new name, whatever [name] is
- searches for a file named specifically DockerFile to build an image from

# Containers
docker ps
- displays running container

docker ps -a
- displays all containers including stopped

docker run [image name]
- create and run a container from an image

docker stop [container]
- stop a container

docker start [container]
- start a container

docker restart [container]
- restarts a container

dock rm [container]
- removes a container

docker logs [container]
- displays container logs

docker logs -f [container]
- displays container logs real time

docker inspect [container]
- displays config and metadata

docker exec -it [container] sh
- execute sh in an interactive terminal inside a container

# Compose
docker compose up
- run inside a directory with a compose.yaml to do whatever compose.yaml instructs

docker compose up -d
- docker compose but detached so it runs services in the background

docker compose down
- stop and remove services (doesn't delete the compose.yaml)

docker compose ps
- show compose-managed containers

docker compose logs
- shows logs composed-managed services

docker compose logs -f
- displays docker compose logs live

docker compose restart
- restart docker compose services

# Maintenance
docker system prune
- remove unused docker objects

docker container prune
- remove stopped containers

docker image prune
- remove unused images

