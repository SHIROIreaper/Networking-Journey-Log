# IP Addressing Cheatsheet

This is a quick reference I'm putting together as I learn about IP addressing and how networks talk to each other. It’s all IPv4 for now since that’s what most tools and systems still use. Keeping it simple and practical.

---

## What is an IP address?

An IP address is just a unique number assigned to a device on a network. Think of it like a house address — it tells data where to go.

IPv4 addresses are 32 bits long and usually written in dotted decimal like:  
`192.168.1.10`

---

## Structure of an IP address

Each IP address is split into two parts:

- **Network part** – identifies the network
- **Host part** – identifies the specific device on that network

Example: `192.168.1.10/24`

- `/24` means the first 24 bits are for the network.
- The rest (8 bits here) are for hosts.

---

## IP Address Classes (just for understanding)

Older IP ranges were grouped into "classes" but now we mostly use CIDR. Still good to know:

| Class | Range                     | Default Subnet Mask | Use For         |
|-------|---------------------------|----------------------|------------------|
| A     | 1.0.0.0 – 126.255.255.255 | 255.0.0.0 (/8)       | Big networks     |
| B     | 128.0.0.0 – 191.255.255.255 | 255.255.0.0 (/16)    | Medium ones      |
| C     | 192.0.0.0 – 223.255.255.255 | 255.255.255.0 (/24)  | Smaller LANs     |

Note:
- `127.x.x.x` is for loopback (i.e., your own system)
- `169.254.x.x` is for APIPA (when DHCP fails)

---

## Private IP address ranges

These are not routable on the internet. They're used inside home or office networks.

| Class | Private IP Range              |
|-------|-------------------------------|
| A     | 10.0.0.0 – 10.255.255.255     |
| B     | 172.16.0.0 – 172.31.255.255   |
| C     | 192.168.0.0 – 192.168.255.255 |

If you're seeing IPs like `192.168.x.x`, that's your local/internal network.

---

## Subnetting basics

Subnetting just breaks bigger networks into smaller ones. Useful for organizing things or saving IPs.

CIDR notation tells us how many bits are used for the network. Fewer host bits = fewer usable devices.

| CIDR | Subnet Mask       | Usable Hosts |
|------|-------------------|---------------|
| /24  | 255.255.255.0     | 254           |
| /25  | 255.255.255.128   | 126           |
| /26  | 255.255.255.192   | 62            |
| /30  | 255.255.255.252   | 2             |

(To get usable hosts: 2^host_bits - 2)

---

## Special IPs in a subnet

Say your subnet is `192.168.1.0/24`:

- Network address: `192.168.1.0`
- First usable: `192.168.1.1`
- Last usable: `192.168.1.254`
- Broadcast address: `192.168.1.255`

You can’t assign the network or broadcast address to any device.

---

## Public vs Private IPs

- **Private IPs** stay inside your network (home, office, etc.)
- **Public IPs** are visible on the internet and assigned by your ISP

Your router usually translates between them using NAT.

---

## Some useful Linux commands

These are some commands I use to check or debug networking stuff:

| What it does          | Command               |
|-----------------------|------------------------|
| Show IP address       | `ip a` or `ifconfig`   |
| Ping a server         | `ping 8.8.8.8`         |
| Trace packet path     | `traceroute google.com`|
| Routing table         | `ip route`             |
| See hostname & IP     | `hostname -I`          |

---

## Related tools to explore

Some tools I’m using or plan to use:

- `nmap` — scan IPs/subnets
- `ping`, `traceroute` — test reachability
- `whois`, `dig`, `nslookup` — get DNS and IP info
- `tcpdump`, `wireshark` — look at actual network traffic

---

This is a living document — I’ll keep updating it as I go deeper into subnetting, IPv6, NAT, and everything else that comes along.
