# Networking Commands

## ss -tulpn

`ss -tulpn`

* Display listening sockets and the processes using them.
* `ss` = Socket Statistics.

Flags:

* `-t` → Show TCP sockets.
* `-u` → Show UDP sockets.
* `-l` → Show only listening sockets.
* `-p` → Show the process using each socket.
* `-n` → Show numeric addresses and ports instead of resolving names.

---

## ss -tan

`ss -tan`

* Show all TCP sockets.

Flags:

* `-t` → TCP only.
* `-a` → Show all sockets (listening and established).
* `-n` → Numeric output.

Useful for viewing active TCP connections.

---

## ss -uan

`ss -uan`

* Show all UDP sockets.

Flags:

* `-u` → UDP only.
* `-a` → Show all sockets.
* `-n` → Numeric output.

---

## tcpdump

`tcpdump -i [interface] [protocol] port [port]`

Examples:

```bash id="eg1"
tcpdump -i eth0
tcpdump -i eth0 tcp
tcpdump -i eth0 tcp port 80
```

* Capture packets traversing an interface.
* Protocol and port filters are optional.

Common flags:

* `-i` → Interface to capture from.
* `-n` → Do not resolve names.
* `-v` → Verbose output.

---

## ip addr

`ip addr`

or

`ip a`

* Show IP addresses and subnet information assigned to interfaces.

---

## ip link

`ip link`

* Show network interfaces.
* Displays interface state (UP/DOWN).
* Displays MAC addresses.

---

## ip route

`ip route`

* Show the routing table.
* Displays default gateway and network routes.

---

## ip neigh

`ip neigh`

* Show IP → MAC address mappings.

Variants:

`ip -4 neigh`

* Show IPv4 mappings only.

`ip -6 neigh`

* Show IPv6 mappings only.

Notes:

* IPv4 uses ARP (Address Resolution Protocol).
* IPv6 uses NDP (Neighbor Discovery Protocol).

---

## ping

`ping [host]`

* Test reachability of a host.
* Uses ICMP (Internet Control Message Protocol).

Examples:

```bash id="eg2"
ping google.com
ping 8.8.8.8
```

---

## nft list ruleset

`nft list ruleset`

* Display the active nftables firewall rules currently loaded into the kernel.

Useful:

```bash id="eg3"
nft list ruleset | grep docker
```

* Search for rules injected by Docker.

Notes:

* nftables rules are loaded into kernel memory.
* Docker dynamically creates nftables rules when containers are started.

---

## nft flush ruleset

`nft flush ruleset`

* Remove all nftables rules currently loaded in kernel memory.

Warning:

* This effectively disables the firewall until new rules are loaded.

---

## traceroute

`traceroute [host]`

* Show the network path packets take to reach a destination.
* Displays each router hop along the path.

Example:

```bash id="eg4"
traceroute google.com
```

---

## tracepath

`tracepath [host]`

* Similar to traceroute.
* Does not require root privileges.
* Displays MTU information.

MTU (Maximum Transmission Unit):

* The largest packet size a network device can transmit without fragmentation.

---

## dig

### IPv4 Lookup

`dig [domain] A`

* Query A records (IPv4 addresses).

Example:

```bash id="eg5"
dig google.com A
```

### IPv6 Lookup

`dig [domain] AAAA`

* Query AAAA records (IPv6 addresses).

Example:

```bash id="eg6"
dig google.com AAAA
```

---

## curl

`curl [URL]`

* Make HTTP requests.
* Output the server response.

Examples:

```bash id="eg7"
curl https://example.com
```

Useful flags:

`-v`

* Verbose mode.
* Shows:

  * DNS lookup
  * TCP connection
  * TLS handshake
  * Request headers
  * Response headers

`-O`

* Download a file and save it using the original filename.

Example:

```bash id="eg8"
curl -O https://example.com/file.txt
```

---

## netcat (nc)

`nc [host] [port]`

Examples:

```bash id="eg9"
nc google.com 80
nc 192.168.1.10 22
```

* Create a raw TCP or UDP connection.
* Extremely versatile networking tool.

Useful flags:

`-v`

* Verbose output.

`-z`

* Scan mode.
* Test whether a port is open without opening an interactive session.

Example:

```bash id="eg10"
nc -vz google.com 443
```

Think of netcat as:

* "Open a raw network connection to something."
* Everything else is built on top of that idea.

