# Linux Networking Demo
A small project I made while learning Linux and different networking technologies.

# Technologies
- Linux
- Docker
- Nginx
- SSH
- nftables

# Current Demo
A Docker Compose deployment in docker/ consisting of an Nginx reverse proxy to a backend service with shared bind-mounted notes.

I load the firewall.conf file with "sudo nft -f firewall.conf" so that port 8080 can be accessed, then restart docker so it applies its own firewall. Not good pratice, but works for a demo.

Docker forwards port 8080 to port 80.
The reverse proxy listens on port 80 and forwards requests to port 8000.
