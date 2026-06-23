# Linux Networking Demo

A repository documenting my learning in using networking and Linux technologies.

The goal of this project is to build practical Linux and networking skills through notes, and deployments.

# Technologies
- Linux
- Docker
- Nginx
- Git
- GitHub
- SSH

# Repository Structure
notes/
docker/
nginx/

# Current Demo
A Docker Compose deployment in docker/ consisting of an Nginx reverse proxy to a backend service with shared bind-mounted notes.

Docker forwards port 8080 to port 80.
The reverse proxy listens on port 80 and forwards requests to port 8000.
