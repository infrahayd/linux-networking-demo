# Linux Networking Demo
The goal of this project is to build practical Linux and networking skills through small deployments.

# Technologies
- Linux
- Docker
- Nginx
- SSH
- nftables

# Current Demo
A Docker Compose deployment in docker/ consisting of an Nginx reverse proxy to a backend service with shared bind-mounted notes.

I load the firewall.conf file with "sudo nft -f firewall.conf" so that port 8080 can be accessed.

Docker forwards port 8080 to port 80.
The reverse proxy listens on port 80 and forwards requests to port 8000.
