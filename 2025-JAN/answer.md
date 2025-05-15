# AACS2034 JAN 2025 Answers

[Link to the paper](https://eprints.tarc.edu.my/31748/1/AACS2034.pdf)

- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)

## Answers

### Question 1

a)

- Subnetting **reduces overall network traffic** and improves performance. It **reduces the broadcast domain size**, which means fewer devices will receive broadcast packets, leading to less congestion on the network.

> Note: Broadcast packets are sent to all devices on a network. If there are many devices on the same network, more broadcast packets will be sent, leading to congestion.

- Subnetting provides **better security** by isolating different network segments. Each subnet can have its **own security policies and access controls**, reducing the risk of unauthorized access to sensitive data.

b) Not agree. It is because VLSM only assigns IP addresses to LANs **based on their actual needs**. This reduces the number of wasted IP addresses, as opposed to FLSM, which assigns the same number of IP addresses to all LANs based on the largest LAN size, leading to more wasted IP addresses.

> The question has a bad wording. The "addressed" supposingly meant "assigned", instead of as in "addressing a problem".

c)

| Migration Technique | Description                                                                                                                                                                        |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dual Stack          | This technique allows both IPv4 and IPv6 to **run simultaneously** on the same network.                                                                                            |
| Tunneling           | This technique **encapsulates IPv6 packets within IPv4 packets**, allowing IPv6 traffic to be sent over an IPv4 network.                                                           |
| Translation         | NAT64 is a translation mechanism on a router that allows **IPv6-only hosts to communicate with IPv4-only hosts**. It **translates IPv6 packets into IPv4 packets and vice versa**. |

d)

i) 8 subnets

ii) 14 usable hosts

> - Observing the IP address of the Server0, it has a subnet mask of `/28`, which means `28` bits for network, and `32 - 28 = 4` bits for host.
> - Total number of addresses = `2^4 = 16`
> - Number of usable addresses = `16 - 2 = 14`

iii)

Broadcast address: `172.16.3.63`

Default gateway: `172.16.3.1`

> - Network address: `172.16.3.0`
> - Broadcast address: `172.16.3.00|1111111 = 172.16.3.63`

iv) Not agree. This is because Server0 is located at a different network segment than Laptop2. Laptop2 requires the default gateway to allow its packets to be routed outside its LAN and reach Server0.

v)

172.16.1.0/25 (Top)
172.16.2.0/25 (Top Right)
192.168.1.0/30 (Top Right Router Link)
192.168.2.0/30 (Bottom Right Router Link)
172.16.4.0/28 (Bottom Right)

### Question 2

a)

i) 120.10.10.1

- Address Class: A
- Default Subnet Mask: `255.0.0.0`
- Network Portion: `120`
- Host Portion: `10.10.1`

ii) 200.40.0.0

- Address Class: C
- Default Subnet Mask: `255.255.255.0`
- Network Portion: `200.40.0`
- Host Portion: `0`

iii) 190.20.10.0

- Address Class: B
- Default Subnet Mask: `255.255.0.0`
- Network Portion: `190.20`
- Host Portion: `10.0`

b)

i) `FE80:0000:0000:1234:0000:0000:0000:0001`

- Rule 1: `FE80:0:0:1234:0:0:0:1`
- Rule 2: `FE80:0:0:1234::1`

ii) `2010:0010:0000:AA00:00BB:0001:0000:0000`

- Rule 1: `2010:10:0:AA00:BB:1:0:0`
- Rule 2: `2010:10:0:AA00:BB:1::`

iii) `2001:1100:0000:0000:0000:00AA:BB00:0000`

- Rule 1: `2001:1100:0:0:0:AA:BB00:0`
- Rule 2: `2001:1100::AA:BB00:0`

c) `show ip route`

d)

- TCP uses **sequence numbers** to label each segment in the order they are sent. This allows the receiver to reassemble the segments in the correct order.
- TCP uses a **three-way handshake** to establish a connection between the sender and receiver. This ensures that both parties are ready to communicate before data is sent.
- TCP uses **flow control** to manage the rate of data transmission between the sender and receiver. When the receiver is busy, it can send a signal to the sender to slow down the transmission rate.

### Question 3

a)

| Message Delivery Options | Description                                                                      |
| ------------------------ | -------------------------------------------------------------------------------- |
| Unicast                  | A message is sent from one sender to one receiver.                               |
| Broadcast                | A message is sent from one sender to all devices on the network.                 |
| Multicast                | A message is sent from one sender to a specific group of devices on the network. |

b)

i) DHCP **automatically assigns IP addresses**, subnet masks, default gateways, and other network configuration parameters to devices on a network. This allows devices to connect to the network without manual configuration.

ii) DNS **translates domain names into IP addresses**, allowing users to access websites using human-readable names instead of numerical IP addresses which are difficult to remember.

iii) FTP **facilitates the transfer of files** between a client and a server. It allows users to upload, download, and manage files on a remote server.

iv) SMTP **facilitates the sending of emails** from a client to a server. It is used to send messages from the sender's email client to the recipient's email server.

c)

- Client broadcast a **DHCP Discover** message to find available DHCP servers on the network.
- The DHCP server responds with a **DHCP Offer** message, which offers a lease of an IP address to the client.
- The client sends a **DHCP Request** message to the server, indicating that it accepts the lease offered by the DHCP server.
- The DHCP server sends a **DHCP Acknowledgment** message to the client, if the lease is valid, to finalize the IP address assignment. Otherwise, it will send a **DHCP Negative Acknowledgment** message to the client.

> Because the client broadcasts the DHCP Discover message, multiple DHCP servers may respond with a DHCP Offer message. The client will only accept one offer and send a DHCP Request message to that server. That's why the lease and acknowledgment process is needed to finalize the IP address assignment.

d)

- Simple Mail Transfer Protocol (SMTP)
- Post Office Protocol (POP)
- Internet Message Access Protocol (IMAP)

### Question 4

i) `4` subnets

ii) `62` host addresses

> Host addresses is the same as usable addresses, because network and broadcast addresses are not host addresses. It might ask for all addresses, which is `64` addresses, but I guess it had a bad wording.

iii) `62` usable host addresses

iv) `255.255.255.192`

v) `0` subnets

vi)

| Department Name | Subnet Address   | First Usable Host Address | Last Usable Host Address | Broadcast Address |
| --------------- | ---------------- | ------------------------- | ------------------------ | ----------------- |
| HR Dept         | `192.168.10.0`   | `192.168.10.1`            | `192.168.10.62`          | `192.168.10.63`   |
| Purchasing Dept | `192.168.10.64`  | `192.168.10.65`           | `192.168.10.126`         | `192.168.10.127`  |
| Admin Dept      | `192.168.10.128` | `192.168.10.129`          | `192.168.10.190`         | `192.168.10.191`  |
| Sales Dept      | `192.168.10.192` | `192.168.10.193`          | `192.168.10.254`         | `192.168.10.255`  |

vii)

| Department Name | Subnet Address / Prefix | First Usable Host Address | Last Usable Host Address | Broadcast Address |
| --------------- | ----------------------- | ------------------------- | ------------------------ | ----------------- |
| Admin Dept      | `192.168.10.0/26`       | `192.168.10.1`            | `192.168.10.62`          | `192.168.10.63`   |
| Purchasing Dept | `192.168.10.64/27`      | `192.168.10.65`           | `192.168.10.94`          | `192.168.10.95`   |
| Sales Dept      | `192.168.10.96/27`      | `192.168.10.97`           | `192.168.10.126`         | `192.168.10.127`  |
| HR Dept         | `192.168.10.128/29`     | `192.168.10.129`          | `192.168.10.134`         | `192.168.10.135`  |
