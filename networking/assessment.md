# Self Assessment

+ Must Read +

    Read the Assessment *[or]* Try to Answer the Questions without Opening the Accordion.

+ What do you need in order to communicate? +
  
  - A common language (for the two ends to understand)
  - A way to address who do you want to communicate with
  - A Connection (so the content of of the communication can reach the recipients)


+ What is TCP/IP? +

    A set of protocols that define how two or more devices can communicate with each other.
    To learn more about TCP/IP, read [here](http://www.penguintutor.com/linux/basic-network-reference)


+ What is Ethernet? +

    Ethernet simply refers to the most common type of Local Area Network (LAN) used today. A LAN—in contrast to a WAN (Wide Area Network), which spans a larger geographical area—is a connected network of computers in a small area, like your office, college campus, or even home.


+ What is a MAC address? What is it used for? +

    A MAC address is a unique identification number or code used to identify individual devices on the network.

    Packets that are sent on the ethernet are always coming from a MAC address and sent to a MAC address. If a network adapter is receiving a packet, it is comparing the packet’s destination MAC address to the adapter’s own MAC address.



+ When is this MAC address used?: ```ff:ff:ff:ff:ff:ff``` +
  
  When a device sends a packet to the broadcast MAC address (`FF:FF:FF:FF:FF:FF​`), it is delivered to all stations on the local network. Ethernet broadcasts are used to resolve IP addresses to MAC addresses (by ARP) at the datalink layer .


+ What is an IP address? +

    An Internet Protocol address (IP address) is a numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication.An IP address serves two main functions: host or network interface identification and location addressing.

+ Explain subnet mask and given an example +

    A Subnet mask is a 32-bit number that masks an IP address, and divides the IP address into network address and host address. Subnet Mask is made by setting network bits to all "1"s and setting host bits to all "0"s. Within a given network, two host addresses are reserved for special purpose, and cannot be assigned to hosts. The "0" address is assigned a network address and "255" is assigned to a broadcast address, and they cannot be assigned to hosts.

    **For Example**

    ```
    | Address Class | No of Network Bits | No of Host Bits | Subnet mask     | CIDR notation |
    | ------------- | ------------------ | --------------- | --------------- | ------------- |
    | A             | 8                  | 24              | 255.0.0.0       | /8            |
    | A             | 9                  | 23              | 255.128.0.0     | /9            |
    | A             | 12                 | 20              | 255.240.0.0     | /12           |
    | A             | 14                 | 18              | 255.252.0.0     | /14           |
    | B             | 16                 | 16              | 255.255.0.0     | /16           |
    | B             | 17                 | 15              | 255.255.128.0   | /17           |
    | B             | 20                 | 12              | 255.255.240.0   | /20           |
    | B             | 22                 | 10              | 255.255.252.0   | /22           |
    | C             | 24                 | 8               | 255.255.255.0   | /24           |
    | C             | 25                 | 7               | 255.255.255.128 | /25           |
    | C             | 28                 | 4               | 255.255.255.240 | /28           |
    | C             | 30                 | 2               | 255.255.255.252 | /30           |

    ```


+ What is a private IP address? In which scenarios/system designs, one should use it? +
  
    Private IP address of a system is the IP address which is used to communicate within the same network. When we want exchange data between two systems on the same network, we use private IP address.

+ What is a public IP address? In which scenarios/system designs, one should use it? +
  
    Public IP address of a system is the IP address which is used to communicate outside the network. Public IP address is basically assigned by the ISP to the system. When we want exchange data between two systems on different networks, we use public IP address.

+ Explain the OSI model. What layers there are? What each layer is responsible for? +

  - Application: user end (HTTP is here)
  - Presentation: establishes context between application-layer entities (Encryption is here)
  - Session: establishes, manages and terminates the connections
  - Transport: transfers variable-length data sequences from a source to a destination host (TCP & UDP are here)
  - Network: transfers datagrams from one network to another (IP is here)
  - Data link: provides a link between two directly connected nodes (MAC is here)
  - Physical: the electrical and physical spec the data connection (Bits are here)

    You can read more about the OSI model in [penguintutor.com](http://www.penguintutor.com/linux/basic-network-reference)

<!-- tabs:start -->

#### **Question**

For each of the following determine to which OSI layer it belongs: 

1. Error correction 
2. Packets routing 
3. Cables and electrical signals 
4. MAC address 
5. IP address
6. Terminate connections
7. 3 way handshake

#### **Answer**

1. Application
2. Network
3. Physical
4. Data link
5. Network
6. Session
7. Transport

<!-- tabs:end -->


+ What delivery schemes are you familiar with? +

    Unitcast: One to one communication where there is one sender and one receiver.

    Broadcast: Sending a message to everyone in the network. The address ff:ff:ff:ff:ff:ff is used for broadcasting.
            Two common protocols which use broadcast are ARP and DHCP.

    Multicast: Sending a message to a group of subscribers. It can be one-to-many or many-to-many.


+ What is CSMA/CD? Is it used in modern ethernet networks? +

    CSMA/CD stands for Carrier Sense Multiple Access / Collision Detection.
    Its primarily focus it to manage access to shared medium/bus where only one host can transmit at a given point of time.

    CSMA/CD algorithm:

    1. Before sending a frame, it checks whether another host already transmitting a frame.
    2. If no one transmitting, it starts transmitting the frame.
    3. If two hosts transmitted at the same time, we have a collision.
    4. Both hosts stop sending the frame and they send to everyone a 'jam signal' notifying everyone that a collision occurred
    5. They are waiting for a random time before sending again
    6. Once each host waited for a random time, they try to send the frame again and so the

<!-- tabs:start -->

#### **Question**

Describe the following network devices and the difference between them: 
  * router
  * switch
  * hub 

#### **Answer**

| Router | Switch | Hub |
| ------- | ------- | ------- |
| Network Layer | Data Link Layer | Physical Layer |
| Works on basis of IP Address | Works on basis of MAC Address | Works on basis of Ethernet Frame |
| Reads the header of incoming packet and forward it to the port for which it is intended there by determines the route | receives a message from any device connected to it and then transmits the message only to the device for which the message is intended | a multiport repeater which can be used to connect multiple devices to a single port |


<!-- tabs:end -->


+ How does a router works? +

    A router is a physical or virtual appliance that passes information between two or more packet-switched computer networks. A router inspects a given data packet's destination Internet Protocol address (IP address), calculates the best way for it to reach its destination and then forwards it accordingly.


+ What is NAT? +

    Network Address Translation (NAT) is a process in which one or more local IP address is translated into one or more Global IP address and vice versa in order to provide Internet access to the local hosts.



+ What is a proxy? How does it works? What do we need it for? +

    A proxy server acts as a gateway between you and the internet. It’s an intermediary server separating end users from the websites they browse.

    If you’re using a proxy server, internet traffic flows through the proxy server on its way to the address you requested. The request then comes back through that same proxy server (there are exceptions to this rule), and then the proxy server forwards the data received from the website to you.

    roxy servers provide varying levels of functionality, security, and privacy depending on your use case, needs, or company policy.


+ What is TCP? How does it works? What is the 3 way handshake? +

    TCP 3-way handshake or three-way handshake is a process which is used in a TCP/IP network to make a connection between server and client.

    A three-way handshake is primarily used to create a TCP socket connection. It works when:

    - A client node sends a SYN data packet over an IP network to a server on the same or an external network. The objective of this packet is to ask/infer if the server is open for new connections.
    - The target server must have open ports that can accept and initiate new connections. When the server receives the SYN packet from the client node, it responds and returns a confirmation receipt – the ACK packet or SYN/ACK packet.
    - The client node receives the SYN/ACK from the server and responds with an ACK packet.


+ What is round-trip delay or round-trip time? +

    From [wikipedia](https://en.wikipedia.org/wiki/Round-trip_delay): "the length of time it takes for a signal to be sent plus the length of time it takes for an acknowledgement of that signal to be received"


+ What is the RTT of LAN? +
  
  Round-trip time (RTT) is the duration in milliseconds (ms) it takes for a network request to go from a starting point to a destination and back again to the starting point.


+ How does SSL handshake work? +

    - A browser attempts to connect to a web site secured with SSL. The browser requests that the web server identify itself.
    - The server sends the browser a copy of its SSL certificate.
    - The browser checks whether it trusts the SSL certificate. If so, it sends a message to the server.
    - The server sends back a digitally signed acknowledgement to start an SSL encrypted session.
    - Encrypted data is shared between the browser and the server.

+ What is the difference between TCP and UDP? +

    TCP establishes a connection between the client and the server to guarantee the order of the packages, on the other hand, UDP does not establish a connection between client and server and doesn't handle package order. This makes UDP more lightweight than TCP and a perfect candidate for services like streaming.

    [Penguintutor.com](http://www.penguintutor.com/linux/basic-network-reference) provides a good explanation.


+ What TCP/IP protocols are you familiar with? +

    | Layer | Protocol |
    | ------- | ------- |
    | Application | HTTP, Telnet, FTP, DNS |
    | Transport | TCP, UDP |
    | Network | IP, ARP, RARP, ICMP |
    | Data Link | Ethernet, 802.3, 802.2, 802.1, 802.0 |
    | Physical | Token Ring, FDDI, ATM, PPP, HDLC, X.25 |


+ Explain "default gateway" +

    A default gateway serves as an access point or IP router that a networked computer uses to send information to a computer in another network or the internet.


+ What is ARP? How does it works? +

    ARP stands for Address Resolution Protocol. When you try to ping an IP address on your local network, say 192.168.1.1, your system has to turn the IP address 192.168.1.1 into a MAC address. This involves using ARP to resolve the address, hence its name.

    Systems keep an ARP look-up table where they store information about what IP addresses are associated with what MAC addresses. When trying to send a packet to an IP address, the system will first consult this table to see if it already knows the MAC address. If there is a value cached, ARP is not used.


+ What is TTL? What does it helps to prevent? +
  
    Time to live (TTL) refers to the amount of time or “hops” that a packet is set to exist inside a network before being discarded by a router. TTL makes sure that a data packet, or packets, won't be circulating indefinitely in a computer network or in an application.

+ What is DHCP? How does it works? +

    It stands for Dynamic Host Configuration Protocol, and allocates IP addresses, subnet masks and gateways to hosts. This is how it works:

    * A host upon entering a network, broadcasts a message in search of a DHCP server (DHCP DISCOVER)
    * An offer message is sent back by the DHCP server as a packet containing lease time, subnet mask, IP addresses, etc (DHCP OFFER)
    * Depending on which offer accepted, the client sends back a reply broadcast letting all DHCP servers know (DHCP REQUEST)
    * Server sends an acknowledgment (DHCP ACK)

    Read more [here](https://linuxjourney.com/lesson/dhcp-overview)


+ Can you have two DHCP servers in the same network? How it works? +

    No, DHCP servers can't be in the same network. DHCP servers are used to allocate IP addresses to hosts. If you have two DHCP servers in the same network, you can use the second DHCP server as a backup server.


+ What is SSL tunneling? How does it works? +

    SSL Tunneling involves a client that requires an SSL connection to a backend service or secure server via a proxy server. This proxy server opens the connection between the client and the backend service and copies the data to both sides without any direct interference in the SSL connection.

+ What is a socket? Where can you see the list of sockets in your system? +
    
    A network socket is a software structure within a network node of a computer network that serves as an endpoint for sending and receiving data across the network. We can see the list of sockets in our system by typing the following command:
    ```Windows
    netstat -ano
    ```
    ```Linux
    ss -s
    ```
    ```MacOs
    netstat
    ```

+ What is IPv6? Why should we consider using it if we have IPv4? +

    IPv6 is a network layer protocol that allows communication to take place over the network. 

    - The IPv4 uses a 32-bit address scheme allowing to store 2^32 addresses which is more than 4 billion addresses. To date, it is considered the primary Internet Protocol and carries 94% of Internet traffic. IPv6 consists of eight groups of four hexadecimal digits which is deployed to fulfill the need for more Internet addresses.
  
+ What is VLAN? +

    VLAN allow you to isolate a network from the rest of the network. It is a way to create a virtual network.

+ What is MTU? +

    Maximum Transmission Unit (MTU) is the largest packet size that can be sent over a network.

+ What happens if you send a packet that is bigger than the MTU? +

    The packet is dropped.

+ True or False?. Ping is using UDP because it doesn't care about reliable connection +

    True. Because UDP is a connectionless protocol.

+ What is SDN? +

    Software-defined networking technology is an approach to network management that enables dynamic, programmatically efficient network configuration in order to improve network performance and monitoring, making it more like cloud computing than traditional network management.

+ What is ICMP? What is it used for? +

    The Internet Control Message Protocol is a supporting protocol in the Internet protocol suite. It is used by network devices, including routers, to send error messages and operational information.

+ What is NAT? How does it work? +

    NAT stands for network address translation. It’s a way to map multiple local private addresses to a public one before transferring the information. Organizations that want multiple devices to employ a single IP address use NAT, as do most home routers.
    For example, your computer's private IP could be 192.168.1.100, but your router maps the traffic to it's public IP (e.g. 1.1.1.1). Any device on the internet would see the traffic coming from your public IP (1.1.1.1) instead of your private IP (192.168.1.100).


+ Which factors affect network performances +

    - Number of Devices on the Network
    - Bandwidth
    - Latency
    - Type of Traffic
    - Number of Transmission Errors

+ Which port number is used in each of the following protocols?: SSH , SMTP, HTTP, DNS, HTTPS, FTP, SFTP +

  * SSH - 22
  * SMTP - 25
  * HTTP - 80
  * DNS - 53
  * HTTPS - 443
  * FTP - 21
  * SFTP - 22

+ What "control plane" refers to? +

    The control plane is the part of the network that decides how to route and forward packets to a different location.


+ What "data plane" refers to? +

    The data plane is the part of the network that actually forwards the data/packets.


+ What "management plane" refers to? +

    Refers to monitoring and management functions.


+ To which plane (data, control, ...) is creating routing tables belongs to? +

    Control Plane.


+ Explain Spanning Tree Protocol (STP) +

    Spanning Tree Protocol (STP) is a protocol that is used to manage the network topology. It is used to ensure that the network is connected and that there are no loops in the network.

+ What is link aggregation? Why is it used? +

    Link aggregation is a technique that allows a network to connect multiple links into a single link. This is done by creating a virtual link that connects all the links together.

+ What is Asymmetric Routing? How do deal with it? +

    Asymmetric routing is a routing protocol that allows a network to route packets to a destination that is not directly connected to the source. 

    To deal with this, adjust the placement of the firewalls or internal routing such that traffic in both directions flows through the same firewall, even if incoming traffic enters the network through a different router than the router that handled the matching outgoing traffic.

+ What overlay (tunnel) protocols are you familiar with? +

    - Virtual Extensible LAN,
    - Network Virtualization using Generic Encapsulation (NVGRE), 
    - Stateless Transport Tunneling (STT), 
    - Generic Routing Encapsulation (GRE), and 
    - Network Virtualization Overlays 3 (NVO3).

+ What is GRE? How does it works? +

    - Generic Routing Encapsulation is a protocol for encapsulating data packets that use one routing protocol inside the packets of another protocol.
    

+ What is VXLAN? How does it works? +

    - An encapsulation protocol that provides data center connectivity using tunneling to stretch Layer 2 connections over an underlying Layer 3 network.


+ What is SNAT? +

    - SNAT is an abbreviation for Source Network Address Translation. It is typically used when an internal/private host needs to initiate a connection to an external/public host. The device performing NAT changes the private IP address of the source host to public IP address.

+ Explain OSPF +

    - The OSPF (Open Shortest Path First) protocol is one of a family of IP Routing protocols, and is an Interior Gateway Protocol (IGP) for the Internet, used to distribute IP routing information throughout a single Autonomous System (AS) in an IP network.

+ What is latency? +

    - Latency is the time it takes for a packet to travel from one router to another.

+ What is bandwidth? +

    - Bandwidth is the amount of data that can be transmitted in a given amount of time.

+ What is throughput? +

    - Throughput is the amount of data that can be transmitted in a given amount of time.

+ When performing a search query, what is more important, latency or throughput? And how to assure that what managing global infrastructure? +

    Latency. To have a good latency, a search query should be forwarded to the closest datacenter.


+ When uploading a video, what is more important, latency or throughput? And how to assure that? +

    Throughput. To have a good throughput, the upload stream should be routed to an underutilized link.

+ What other considerations (except latency and throughput) are there when forwarding requests? +

    - Transmission Medium
    - Network Congestion
    - Packet Loss and Error Rate
    - Cache

+ Explain Spine & Leaf +

    Spine and Leaf Architecture is a two-layer, full-mesh topology composed of a leaf layer and a spine layer, with the leaf and spine switches. 

    Spine Layer – serves as the backbone of the network similar to the core layer in our three-tier design. It is where we can find the spine switches which can be a Layer 3 switch. Each Layer 3 port is connected to the underlying Layer 2 leaf switch.

    Leaf Layer – connects to end devices similar to the access layer in our three-tier design. It is where the leaf switches which connect to all spine switches reside. In our example above, we have servers that connect to leaf switches. In a data center environment, it can be any kind of server, like web server, application server, database server, or storage server.

+ What is Network Congestion? What can cause it? +

    Network congestion is a condition in which a network is unable to send data packets at the rate it is being requested. This can happen when the network is under heavy load, or when the network is congested by other devices.

+ What can you tell me about UDP packet format? What about TCP packet format? How is it different? +

    - UDP Packet Format:
        - Source Port
        - Destination Port
        - Length
        - Checksum
        - Data
    - TCP Packet Format:
        - Source Port
        - Destination Port
        - Sequence Number
        - Acknowledgement Number
        - Data Offset
        - Reserved
        - Flags
        - Window
        - Checksum
        - Urgent Pointer
        - Data

+ What is the exponential backoff algorithm? Where is it used? +

    - Exponential Backoff Algorithm is a network protocol that is used to manage the network topology. It is used to ensure that the network is connected and that there are no loops in the network.

+ Using Hamming code, what would be the code word for the following data word 100111010001101? +

    00110011110100011101


+ Give examples of protocols found in the application layer +

  * Hypertext Transfer Protocol (HTTP) - used for the webpages on the internet
  * Simple Mail Transfer Protocol (SMTP) - email transmission
  * Telecommunications Network - (TELNET) - terminal emulation to allow client access to telnet server
  * File Transfer Protocol (FTP) - facilitates transfer of files between any two machines
  * Domain Name System (DNS) - domain name translation
  * Dynamic Host Configuration Protocol (DHCP) - allocates IP addresses, subnet masks and gateways to hosts
  * Simple Network Management Protocol (SNMP) - gathers data of devices on the network


+ Give examples of protocols found in the network Layer +

  * Internet Protocol (IP) - assists in routing packets from one machine to another
  * Internet Control Message Protocol (ICMP) - lets one know what is going such as error messages and debugging information


+ What is HSTS? +
  
    HTTP Strict Transport Security is a web server directive that informs user agents and web browsers how to handle its connection through a response header sent at the very beginning and back to the browser. This forces connections over HTTPS encryption, disregarding any script's call to load any resource in that domain over HTTP.

    Read more [here](https://www.globalsign.com/en/blog/what-is-hsts-and-how-do-i-use-it#:~:text=HTTP%20Strict%20Transport%20Security%20(HSTS,and%20back%20to%20the%20browser.)

+ What is the Internet? Is it the same as the World Wide Web? +

    The internet refers to network of networks, transferring huge amounts of data around the globe.
    The World Wide Web is an application running on millions of server, on top of the internet, accessed through what is know as the web browser


+ What is the ISP? +

    ISP (Internet Service Provider) is the local internet company provider.