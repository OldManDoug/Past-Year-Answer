https://eprints.tarc.edu.my/cgi/users/login?target=https%3A%2F%2Feprints.tarc.edu.my%2F27893%2F1%2FAACS2034.pdf
(Link to the Past year- not sure how to make the link to question

Question 1.
a.(i) sh ip route
(ii)route table
(iii) 6 routes which are directly connected and remote routes
(iv)172.16.18.0/24 and 209.165.200.0/30 // is connected by 172.18.3.1(IP address)  --> remote route
(v).172.16.18.0/24  192.168.10.0/26 //if the word is had been means VLSMéd then 209.165.200.0/24 192.168.10.0/24
actual answer: private IP addresses, public IP address /local ip 
(vi) As a default gateway and to connect to a networking device(router or switch) that is connected directly to R1. Used to assign an IP to a host connected to the interface Gi 0/1   //because has an L(variably subnetted) it is used to assign host addresses on a network 
(vii)Packet will be dropped. Reason: 210 network address is greater than all the network subnet addresses on the route table. So the packet cannot pass through the gateway.

b.  Connectionless --> does not need a connection to Work
    BestEffort--> will not guarantee packet delivered safely and correctly
    MediaIndependent --> can be used on any media avaliable to pass data. 
c. IPV4 VS V6(2)
 ipv6 has smaller header size, ipv4 header is 20 bit and ipv6 is 8 bit
 ipv6 has lesser fields inside so accomodates more bits to the address which increases address space
Question 2
A.
(i) Class A  DEFAULT SUBNET MASK : 255.0.0.0 (ii). Class C Default subnet MASK = 255.255.255.0 (iii). Class B Default subnet MASK = 255.255.0.0
b. (New but may come out) - Class D is a multicast address so its purpose is used to connect from one to multiple selected hosts in a network. Ip address : 234.10.10.0

c. Migration technique - DS TUN TRANS
Dual Stack - both ipv4 and ipv6 run at the same time 
TUNneling - encapsulate ipv6 packet to ipv4 and vice-versa done by any networking device or host 
TRANSlation - encapsulate ipv6 packet to ipv4 and vice-versa by router

d. IPV6 COMPRESSION R1- NO lead 0 R2- ::  - need to have 8 hextets
(i) 2001:0db8:CAFE:FDFF:000A:0100:0000:0001
Rule 1: eliminate leading 0 --> 2001:db8:CAFE:FDFF:A:100:0:1
Rule 2: use :: --> 2001:db8:CAFE:FDFF:A:100::1

(ii)FE80:0000:0000:0000:020A:F3FF:FEBB:A594 
Rule 1: eliminate leading 0 --> FE80:0:0:0:20A:F3FF:FEBB:A594
Rule 2: use :: --> FE80::20A:F3FF:FEBB:A594

(iii)FDFF:0000:A100:9800:0000:AAAA:BBBB:CCCC 
Rule 1: eliminate leading 0 --> FDFF:0:A100:9800:0:AAAA:BBBB:CCCC
Rule 2: use :: --> //If the strings(of 0's) are equal, the first string should use the double colon (::)
FDFF::A100:9800:0:AAAA:BBBB:CCCC 

Q3:  192.168.8.9/27 - base here how many bit borrowed
a. /27 = find the Class of network, then the default mask(255.255.255.0 /24), is (Class C- 192 to 223 : 
)    Fromula: New prefix - default prefix    (27-24 = 3)  - 3 borrowed bits. 
b. Network address( refer back to Class TYPE, and first network address is always end .0)
11000000   10101000  00001000   11101001 /27, hav an extra 3 bits 
111111111  11111111  11111111   00000000 /24

SUBENT AND 11000000 10101000 00001000  00000000 = bin form, which convert to decimal
Network address(in decimal) = 192.168.8.0 

c. TOTAL USABLE HOSTS= **the word useable means you must -2 ** use the 2^N ,then 8-N = H, finally 2^H-2(usable) 
TOTAL HOST = use the 2^N ,then 8-N = H  
8-N, N=3 8-3 = 5 BIT is for Host   Useable host: 2^5 -2 = 30 useable hosts

d. 192.168.8.9 is broadcast yes or no? --> NO/yes = 1m, find the broadcast address then compare with the question's question +2m ! 
Answer:  NO because the broadcast address is the LAST IP in a subnet/ network. The last IP address for the network is 192.168.8.31. therefore 192.168.8.31 is the actual broadcast address, not 192.168.8.9 . 

3b. (VLSM) - cant make table here 
192.168.10.0/24 (CLASS C) 
Branch Name / WAN Link
Prefix length(/X)
Subnet Address
First Usable Host Address
Last Usable Host Address
Broadcast
Accounting
/26
192.168.10.0
192.168.10.1
192.168.10.62
192.168.10.63
IT
/27
192.168.10.64
192.168.10.65
192.168.10.94
192.168.10.95
Purchasing
/27
192.168.10.96
192.168.10.97
192.168.10.126
192.168.10.127
Warehouse
/28
192.168.10.128
192.168.10.129
192.168.10.142
192.168.10.143
SALES
/28
192.168.10.144
192.168.10.145
192.168.10.158
192.168.10.159
R-R(Router-router) /WAN1
/30
192.168.10.160
192.168.10.161
192.168.10.162
192.168.10.163

Q4. (My own Question target come out 202501 Final Exam FCN)
a. Examine the main function and state the well-known port numbers of the protocols as follows: 
(i) 
Hypertext Transfer Protocol (HTTP) 
(3 marks)    --> Use to communicate and send and recieve data and resposne reuqest from websites and web base applications. Port number is 80
(ii) 
File Transfer Protocol (FTP) 
(3 marks)  --> Use in transferring, reading,and uploading of files to a file server, Port number is 20 for data and 21 for control 
(iii) 
Simple Mail Transfer Protocol (SMTP) 
(3 marks)  -->  determine how emails/mails are sent, received and processed by mail client and server. Port number 25
(iv) 
Post Office Protocol 3 (POP 3) 
(3 marks)  --> Use for retrieving email(s) from mail server. Port number is 110 

b. SMTP, POP, ICMP
c. Common message types is GET POST PUT 
GET - is HTTP message type to REQUEST web page or HTML or data from a HTTP Server by HTTP client
POST - is a HTTP message type to SEND web data usually in HTML Form to HTTP Server
PUT - is a HTTP message type to UPLOAD RESOURCES(usually images or files) into HTTP  server
