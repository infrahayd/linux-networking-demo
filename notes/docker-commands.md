# Docker Commands

## Core Concepts

### Image

* A blueprint or template used to create containers.
* Images are read-only.
* Containers are created from images.

Example:

```text
nginx image
↓
docker run nginx
↓
nginx container
```

---

### Container

* A running instance of an image.
* Has its own filesystem, processes, and network namespace.
* Can be started, stopped, restarted, or removed.

---

### Volume

* Persistent storage managed by Docker.
* Data survives container deletion.

---

# Images

`docker images`

* List downloaded images.

---

`docker pull [image]`

* Download an image from Docker Hub or another registry.

Example:

```bash
docker pull nginx
```

---

`docker rmi [image]`

* Remove an image.

Example:

```bash
docker rmi nginx
```

---

`docker build -t [name] .`

Flags:

* `-t` → Tag the image with a name.

Arguments:

* `.` → Build context (current directory).

Example:

```bash
docker build -t myapp .
```

Notes:

* Docker searches for a file named:

```text
Dockerfile
```

in the build context by default.

* Builds a new image from the Dockerfile.

---

# Containers

`docker ps`

* Show running containers.

---

`docker ps -a`

* Show all containers, including stopped containers.

---

`docker run [image]`

* Create and start a container from an image.

Example:

```bash
docker run nginx
```

---

`docker stop [container]`

* Stop a running container.

---

`docker start [container]`

* Start an existing stopped container.

---

`docker restart [container]`

* Restart a container.

---

`docker rm [container]`

* Remove a container.

* Container must usually be stopped first.

---

`docker logs [container]`

* Show container logs.

---

`docker logs -f [container]`

Flags:

* `-f` → Follow logs live.

* Display logs in real time.

---

`docker inspect [container]`

* Display detailed metadata and configuration.

Examples:

* Network configuration
* Mounted volumes
* Container IP address
* Environment variables

---

`docker exec -it [container] sh`

Flags:

* `-i` → Interactive (keep stdin open).

* `-t` → Allocate a terminal.

* Execute a shell inside a running container.

Example:

```bash
docker exec -it backend sh
```

If Bash exists:

```bash
docker exec -it backend bash
```

---

# Docker Compose

`docker compose up`

* Read `compose.yaml`.
* Create and start services defined in the file.

---

`docker compose up -d`

Flags:

* `-d` → Detached mode.

* Run services in the background.

---

`docker compose down`

* Stop and remove compose-managed containers and networks.

Notes:

* Does **not** delete:

  * compose.yaml
  * Images
  * Volumes (unless explicitly requested)

---

`docker compose ps`

* Show compose-managed containers.

---

`docker compose logs`

* Show logs from compose-managed services.

---

`docker compose logs -f`

Flags:

* `-f` → Follow logs live.

---

`docker compose restart`

* Restart compose-managed services.

---

# Maintenance

`docker system prune`

* Remove unused Docker objects.

Removes:

* Stopped containers
* Unused networks
* Dangling images

---

`docker container prune`

* Remove stopped containers.

---

`docker image prune`

* Remove unused images.

---

# Volumes

`docker volume ls`

* List Docker-managed volumes.

---

`docker volume create [name]`

* Create a volume.

Example:

```bash
docker volume create notes
```

---

`docker volume inspect [name]`

* Show volume details.

Examples:

* Mount location
* Driver
* Metadata

---

`docker volume rm [name]`

* Remove a volume.

Example:

```bash
docker volume rm notes
```

---

`docker volume prune`

* Remove all unused volumes.

Warning:

* Can permanently delete data stored in unused volumes.

---

# Useful Commands

`docker network ls`

* List Docker networks.

---

`docker network inspect [network]`

* Show network details.

---

`docker stats`

* Live CPU, RAM, and network usage for running containers.

---

`docker system df`

* Show Docker disk usage.

Useful for checking:

* Images
* Containers
* Volumes
* Build cache

---

# Common Workflow

Pull image:

```bash
docker pull nginx
```

Run container:

```bash
docker run nginx
```

View running containers:

```bash
docker ps
```

Inspect logs:

```bash
docker logs CONTAINER
```

Enter shell:

```bash
docker exec -it CONTAINER sh
```

Stop container:

```bash
docker stop CONTAINER
```

Remove container:

```bash
docker rm CONTAINER
```

