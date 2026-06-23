ss -tulpn
- -t > show tcp sockets
- -u > shows udp sockets
- -l > listening only
- -p > processes using the socket
- -n > numeric output instead of resolve name
- shows socket statistics (what ss stands for) listening ports and processes utilizing them

ss -tan
- -a > all sockets, listening and established
- best for tcp only

ss -uan
- self explanatory based on previous explanation

tcpdump -i [interface] [protocol] port [port]
- captures packets flowing through parameters, protocol is optional

ip addr / ip a
- displays ips and subnets on interfaces

ip link
- shows interfaces, mac addresses, and up/down state

ip route
- shows routing table

ip neigh
ip -4 neigh for ipv4 specifically
ip -6 neigh for ipv6 specifically
- displays ipv4 and ipv6 -> mac mappings (from arp for ipv4 and ndp for ipv6)

ping [host]
- uses icmp

nft list ruleset
- can pipe this through grep for specific hooks like what docker injects
- nftables firewall rules are loaded on boot, as for Docker on startup. Fun fact, removing Docker's firewall rules without restarting will make it break. 

nft flush ruleset
- flushes the ruleset from kernel memory

traceroute [host]
- shows packet path

tracepath [host]
- traceroute except no root reqiured and shows mtu information (maximum transmission unit, largest packet in bytes a network device can send without having to break it up) fragmentation

dig [domain] A
- dns lookup ipv4

dig [domain] AAAA
- dns lookup ipv6

curl [URL]
- -v -> verbose, shows dns lookup, tcp connectiodn, tls handshake, req and resp
- -O -> download a file and save with the original filename
- http request and outputs response

nc [host] [port]
- -v -> verbose
- -z -> don't open a session just test connetion
- this command literally just creates a raw connection, so it's pretty versatile
