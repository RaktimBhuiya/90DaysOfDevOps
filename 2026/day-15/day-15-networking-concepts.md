# Day 15 – Networking Concepts: DNS, IP, Subnets & Ports

## Task

**Task 1: DNS – How Names Become IPs**
**What happens when you type google.com in a browser?**
- The browser asks the DNS resolver to translate google.com into an IP address.
- DNS returns one or more IP addresses associated with the domain.
- The browser establishes a TCP connection (and TLS for HTTPS) to the IP address.
- The browser sends an HTTP/HTTPS request and receives the webpage content.

**DNS Record Types**
|Record|	Purpose|
|A	|Maps a domain name to an IPv4 address.|
|AAAA|	Maps a domain name to an IPv6 address.|
|CNAME|	Creates an alias from one domain name to another.|
|MX|	Specifies the mail servers responsible for receiving email for a domain.|
|NS|	Specifies the authoritative name servers for a domain.|

- dig google .com (google.com.      9       IN      A       172.253.62.100)

**Task 2: IP Addressing**

**What is an IPv4 Address?**
An IPv4 address is a 32-bit logical address used to identify devices on a network.
It is divided into 4 octets separated by dots.
Each octet ranges from 0 to 255.

**Example:**

192.168.1.10

**Structure:**

192 . 168 .  1 .   10
 ↑     ↑     ↑    ↑
Octet Octet Octet Octet

**Public vs Private IP**

- Public IP - Routable on the Internet and globally unique(8.8.8.8)
- Private IP - Used inside private networks and not routable on the Internet(192.168.1.10)

**Private IPv4 Ranges**
Range	CIDR
10.0.0.0 – 10.255.255.255	10.0.0.0/8
172.16.0.0 – 172.31.255.255	172.16.0.0/12
192.168.0.0 – 192.168.255.255	192.168.0.0/16

- Memorize these three ranges—they are commonly asked in interviews.

- ip addr show(Identify My Private IP).

### Task 3: CIDR & Subnetting

**What does /24 mean in 192.168.1.0/24?**

- The /24 is the CIDR prefix length.
the /24 means the first 24 bits are used for the network portion.

Since the total is 32 bits:

32 total bits - 24 network bits = 8 host bits
**It means:**

24 bits = Network portion
8 bits  = Host portion

**IPv4 has 32 bits total:**

11111111.11111111.11111111.00000000
   255      255      255      0

**Subnet Mask:**

255.255.255.0

**How many usable hosts?**
Formula
Usable Hosts = 2^(Host Bits) - 2

Subtract 2 because:

1 Network Address
1 Broadcast Address
/24
Host Bits = 8

2^8 = 256 IPs
256 - 2 = 254 usable hosts
/16
Host Bits = 16

2^16 = 65,536 IPs
65,536 - 2 = 65,534 usable hosts
/28
Host Bits = 4

2^4 = 16 IPs
16 - 2 = 14 usable hosts

**Why do we subnet?**
Divide large networks into smaller manageable networks.
Reduce unnecessary broadcast traffic.
Improve security and network organization.
Efficiently allocate IP addresses.

Example:

Production Subnet : 10.0.1.0/24
Database Subnet   : 10.0.2.0/24
Management Subnet : 10.0.3.0/24

Instead of putting everything in one large network.

**CIDR Table**
CIDR	Subnet Mask	Total IPs	Usable Hosts
/24	-> 255.255.255.0 ->	256	-> 254
/16	-> 255.255.0.0	-> 65,536	-> 65,534
/28	-> 255.255.255.240	-> 16	-> 14

**What is a Port? Why do we need it?**

A port is a logical communication endpoint used by applications and services on a computer.

- An IP address identifies a device.
- A port identifies a specific service running on that device.

**Example:**

172.31.0.149:22
│            │
IP Address   Port

Without ports, the operating system wouldn't know whether incoming traffic is for SSH, a web server, a database, etc.

**Common Ports***
Port	Service
22	SSH
80	HTTP
443	HTTPS
53	DNS
3306	MySQL
6379	Redis
27017	MongoDB

### Task 5: Putting It Together

1. You run curl http://myapp.com:8080 — what networking concepts are involved?
- DNS resolves myapp.com to an IP address.
- IP routing sends packets to the destination host.
- TCP establishes a connection to port 8080.
- HTTP operates at the application layer and sends the request to the web application.

2. Your app can't reach a database at 10.0.1.50:3306 — what would you check first?
- Verify network connectivity using ping 10.0.1.50 (if ICMP is allowed) and check the route.
- Confirm the database service is running and listening on port 3306 using ss -tulpn.
- Check firewall rules, AWS Security Groups, NACLs, and ensure the application can reach 10.0.1.50:3306.

**Example commands:**

- nc -zv 10.0.1.50 3306
- ss -tulpn | grep 3306
- telnet 10.0.1.50 3306

**A common troubleshooting flow is:**

- DNS → Network Connectivity → Port Reachability → Service Status → Firewall/Security Groups