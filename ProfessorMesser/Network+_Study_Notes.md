**OSI Model Open systems interconnection model**

What is OSI?
Osi is a reference that we use to understand and explain networking concepts. We use it to make our and other workers life easier. It shows us how a connection occurs, what happens in a connection, what are the steps. It also helps us when we are trying to fix something broken.

These are the layers..
7- Application
6- Presentation
5- Session
4- Transport
3- Network
2- Data link
1- Physical

The Physical Layer
The bits live here, it includes physical and raw connection.
Hub is in this layer too because it is dumb, technically it is a dumb switch.
Ethernet, cat cables,wifi,hub.

The data link layer
In this layer we use the mac addresses on our devices and hosts. The NIC (Network interface card) in our devices have a mac address, the first 3 octets show the manufacturer and the last 3 octets are random. fyi. we can change our mac addresses. Generally we use switches in this layer because switches use mac addresses to identify hosts and bring packets to them.

The network layer
The protocol we use in this layer is the internet protocol (ip). This layer includes routers. Routers use ip's to identify hosts on a local or public internet. Everyone has a unique ip address in a LAN and every modem has a unique public ip provided by their isp's. We can say that this isnt physical anymore.

The transport layer
In this layer we use ports. Also we use the TCP and UDP protocols for sending and receiving packets. TCP is a slower but reliable way to send and receive packets. UDP is way faster but not too reliable, means that the packet may be dropped or the integrity of it may be broken. This also helps us identify the host in a better way.

The session layer
This layer opens ,maintains and closes the connection between hosts like a telephone call. It handles the connection.

The presentation layer
This layer has SSL/TLS protocols. It encrypts and decrypts data. This layer works with the application layer and this is the layer that happens prior to what we see on our screen.

The application layer
This layer is what we see with our eyes on the screen. This layer has protocols like http, ftp, smtp, pop3.

NETWORKING DEVICES

When we enter a database station we see a lot of racks with devices on them, these are network devices. Network devices are used for a lot of things. We can install new technology devices in our system but also can install the same devices too. But it takes some time to remove the devices.

Switch
This device works with mac addresses, it is in the layer 2 of the osi model. It allows us to send packets in our LAN. There is also something we call L3 switch. Basically it is a switch with a router built into it. It is in both layer 2 and the layer 3 in the osi model. It has a power over ethernet module. Also it works with the hardware built into it called asic (Application specific integrated circuit)

Router
This device works with ip addresses and it is in layer 3 of the osi model. Routers allow us to send data to different ip subnets. It could be an ip subnet next to our lan in the datacenter or it could be an ip subnet in the other side of the world.

Firewall
Firewalls are used to control network traffic. Traditional firewalls use the tcp and udp ports to control incoming and outgoing traffic. Traditional firewalls only look at the headers of the packets. New generation firewalls, the ones used in the modern day use the application layer protocols while controlling what is going in and out. traditional firewalls use up to layer 3-4 on the osi model while ngfw's use the layers up to 7. They also use ip's to make decisions on which packets to filter. They stand between the lan and wan, ingress and egress. ngfw's also have a vpn built in to encrypt data and connect to other firewalls across the internet. They also have ids/ips built in too alongside the nat protocol which transforms our private ip's of our devices to public ip which the isp gives us. Public ip's are unique.

Ids/Ips
Ids and ips is used to detect intrusions and malwares sent to our systems. Ids is a passive system, it creates an alert when an intrusion or malware is detected but it doesnt prevent it from entering the system. Ips on the other hand is an inline system. Every packet must go through the ips system. It stands in the network and stops the malware or the threat actor before stepping in our network. They do this by signatures. These signatures have attack patterns and known exploits in them. If an ips or ids system matches those signatures to incoming packets they do what they have to do.

Methods
Signature based: matches traffic agains a DB of knowsn attack patterns
Anomaly based: Looks how normal traffic looks like and alerts when something weird happens
Policy based:  Alerts when violates a defined rule

Internet => Firewall => IPS >= Network
                    IDS

Load balancer
Load balancers are used to prevent server outages by distributing the users into different servers called server pool or server farm. When one of those servers go out of service due to some issue, load balancers can detect the server that is down, take that out of the list and continue to balance the usage of servers. Load balancers also use algorithms to determine which server gets the next request. Load balancers also include Tcp, ssl offloading, caching content switching and prioritizing.

Proxies
When a host want to connect to a server and sen packets to it, the packet is first sent to the proxy server, then the proxy server sends that packet to the server on their(proxies) behalf. Also proxy servers check for malicious code or exploits in incoming packets so it kinda acts like a firewall too. We can also use it to set username and passwords to connect to the internet with the access control list. Forward proxies sit between the hosts and the internet, reverse proxies sit between the internet and internal servers. We can give load balancers as an example to a reverse proxy. There are two types of proxies transparent and  non transparent, when we are using a transparent proxy the user doesnt really know that they are using a proxy, they think that they are connecting to the internet directly but thats not the case, usually our isp provider implements this in our network. On the other hand, the user knows that they are using a proxy when there is a non-transparent proxy. Also a proxy terminates our connection and opens a new seperate connection to the  destination. 

NAS Network attached storage
It is a storage technique used to store documents, files.. in datacenters. The downside of this is when we want to change something in a file we need to copy the whole while to our system. That takes up a lot of space and takes a lot of time when the file is huge.

SAN Storage area network
It is used to store blocks. the main difference from nas is we have block-level access to files. What this means is that we dont need to copy the whole file to change something in it, we can copy the block of where we want to make a change. This comes in very handy when we are dealing with big files.
Also on both nas and san, since we need very high bandwith for them, we might want to use an isolated network and high speed network topologies.
We can think of san as a virtually attached hard drive and nas as a filesystem 

Access point
Access points are used in enterprise organizations or big buildings to connect devices to the wireless network across everywhere in the building. It only has a single purpose, to provide wireless connection. It is not a wireless router like the ones in our houses which is a router and an access point at the same time. AP is in the layer 2 of osi.  The access point is a bridge between the wired and wireless network. It extends the wired network to wireless network. 

NETWORKING FUNCTIONS

CDN (Content Delivery Network)
When we are using the internet and go into a website. We usually arent going to the website server directly. We are going into the server cached in a cdn. But there is an exception for this which is if the server is not cached in the cdn we need to go back to the origin server and after we do that the cdn caches that website and when we want to access that website again we can see that there is a big difference in latency. For example im in Turkey and want to access to a site in Usa, Instead of going all the way to that server im going to the cdn which is closer to me and get a faster connection and delay.

VPN (Virtual Private Network)
Vpn's create a virtual private network tunnel between us and the destination. In this tunnel the data we sent is encrypted which makes our data content unreadable to threat actors, isp's etc. But still our isp can see that we are connected to a vpn and how much data we are sending. At the end of this tunnel our data is decrypted and got to the destination successfully. The hardware that do the encryption and decryption is contentrator or head-end. When we visit a website by using a vpn, the website sees the ip of the vpn server we are using instead of our public ip address which makes us more private. We also use vpn's to connect to enterprise networks. We may use a hardware to use a vpn if there are a lot of users who are going to use the vpn, but if we are in a small business or just using vpn in our home wifi we may use the manufacturers software to do so. Operating systems also come with default built in vpn clients.

QoS (Quality of Service)
QoS allows us to set the bandwith usage and queue priority on services. The higher prority services need more bandwith usage, so we give those services more priority. Lower priority services get lower bandwith usage and in return work slower. We can configure these on our routers, switches and firewalls. For example there's a udp video player and a tcp mailing service we are using. In order for our video player to function efficiently with minimum packet dropping we need to give it more priority in terms of bandwith usage. Our tcp service can work with lower levels of resources because if a packet gets dropped or fails to go to its destination the tcp service can still reacquire that missing packet without needing to start the connection from the beginning .

TTL (Time To Live)
As we may know computers are super efficient at automating tasks on a level which humans cant really do on their own. But there is a side effect to this which the the system might get into a loop and repeat the same task over and over again. To prevent this we have built a function called ttl. What this does is it drops the packet or stops the process when the process iterate a certain number of times, we may also select a duration time. It may also be used to clear a cache after a desired amount of time passes.
In ip we use ttl to drop the packet after a certain amount of hops. If the maximum amount of hops are reached the packet is dropped. default ttl on linux is 64 and 128 on windows. ttl gets decreased by the router on each hop that happens.
In dns ttl functions different. It is measured by the duration of the ip address that stays in our local cache. When we go into a website using the dns protocol, dns looks up the ip address of the domain name and allows us to access that website without having to remember the ip adress of that website. So after accessing that website the dns record of it is stored in our cache which allows us to access to that website faster in the until the duration that is set by the ttl is over. 

CLOUD
In the modern technology era, we can deploy multiple virtual devices with a click of a mouse on a system. We can deploy servers, network devices etc. This makes it very efficient for user accessibility and for the cloud owners since implementing it provides us ease of management. Clouds also have multitenancy which means that a lot of users can use a single cloud environment at the same time while their data is isolated from others.
For example we have 100 physical servers in our enterprise, all those servers are connected with switches, load balancers.. with redundancy and availability. We can migrate those servers to the cloud and make a single big cloud server with our server farm inside it.

NFV (Network Function Virtualization)
What this does is, it makes our network devices (routers, switches, load balancers, firewalls..) virtual. We can deploy these network devices easily with a click and configure them aswell. Virtualizing our devices lowers the costs dramatically. For example deploying and configuring a firewall normally takes days or weeks but when we use virtualization we can deploy a new firewall in our system in minutes or hours.

VPC (Virtual Private Cloud)
We use these in our public cloud to seperate different applications from each other. There may be more than one vpc in a cloud system. We may also want these vpc's to be able to connect to each other and share resources when needed so we use a transit gateway to do that. We can think of it as a virtual router. Also if remote hosts are going to access these vpc's we might aswell implement a vpn for private and safe connection to our cloud.

Connecting to the cloud
it is common to use vpn's to connect to vpc's and cloud environments. But what if we want to make our cloud accessible to everyone in the internet. To make that happen, we use internet gateways (IGW) for clouds and also we use vpc nat gateway to provide our cloud a public ip address for our vpc's to connect to the internet, when we use vpc nat gateways there is no public ip assigned to the gateway and because of that users cant make a connetion to that gateway, there is only outgoing traffic to the internet from our vpc's. Vpc's are similar to lan's, they are isolated private networks while being multitenant.

VPC ENDPOINTS
Also vpc endpoints allows vpc's on the same cloud providers to have a direct connection.
If we have a local storage on another cloud provier and want to connect our vpc to that storage, we can either use vpc internet gateway for our vpc that is on a public subnet or a vpc endpoint for a private subnet vpc.

Security groups and lists
Cloud providers also include a built in firewall for us to manage inbound and outbound traffic. We can use it to control osi layer 4 (tcp,udp) and layer 3 (ip,ip blocks) protocols.

Network security list
We can apply security rules to entire ip subnets with this. Every instance in that subnet gets assigned with the rules we configure, this is why it lacks granularity. Also nsl is stateless, meaning we need to configure both inbound and outbound traffic for it to work correctly.

Network security group
We can assign security rules to specific virtual nic's in our vpc's.
This is more granular than network security lists.
It is also more efficient and safer.
We can assign different rules to instances in the same ip subnet.
Nsg is stateful, meaning we dont have to configure both inbound and outbound traffic, when we configure the inbound, outbound is configured automatically.

cloud deployment models
Public: Everyone on the internet can access your cloud server.
Private: Your own virtualized local data center.
Hybrid: mix of both.

Software as a service (SaaS)
This service provides us with an application that is managed and updated by the provider. We dont need to do any local installation or configuration, we can just use the app by logging in. Also our data is sent to a third party cloud service.
Simply the application is all ready for the user.
Examples include office apps and google mail, you just log in and use it.

Infrastructure as a service (IaaS) 
What this service means is, we are using the hardware on the cloud and build our own application on top of it. We are responsible for installing, managing and upgrading that software. Our data is still out there in a third party cloud but we have more control over access and security of it.
Examples include AWS EC2, google compute engine, microsoft azure. You get a virtual machine and you install whatever os and software you want.

Platform as a service (PaaS)
This is a middleground between SaaS and IaaS. This is where we build our own application on a platform that is maintained by its providers. Also cloud providers give us all necessary tools to build our own application from scratch. We dont have direct control of the runtime or infrastructure.
Example include heroku, google app engine. You write your applciation code and push it. The platform handles everything underneath.

Introduction to internet protocol
Ip's are used to bring data from one place to another. We can think of ip's as trucks, roads as the internet (lan,wan,ethernet), packets inside the trucks as the tcp and udp protocol and things in the packets as our data. As you can see there is a encapsulation process here.

ethernet header---ethernet payload---ethernet trailer
ethernet header---IP---IP payload---ethernet trailer
ethernet header---IP---TCP or UDP---TCP or UDP payload---ethernet trailer
ethernet header---IP---TCP or UDP---HTTP---ethernet trailer

As you see there is either tcp or udp in the ip payload.. Lets see the differences between them.

TCP-UDP 
They are both used to move data from one place to another over the internet.
Both of them are on OSI layer 4, the transport layer.
Both of them use multiplexing which means that they are able to move multiple applications simultaneously between two hosts. at the same time

TCP Transmission control protocol
is connection-oriented which means that there is a formal process of connection between the sender and receiver. This process is named "three way handshake". First the sender sends a syn packet which means the request to connect, then the receiver sends back a syn-ack packet, and after that  the sender sends a ack packet to confirm they received what was sent.
In this process, the sender knows if the packet sent is successfully arrived at the receiver. This process happens by sending ACK (Acknowledgement)
Also if something happens and some packets could not be sent or dropped during the process, the sender understands that and send the missing packets again to the receiver, this means that this protocol is reliable.
Also the receiver can tell the sender to send packets slower or faster, which means the sender has flow control in this situation.
To simplify;
Tcp is,
Connection oriented.
Has flow control.

UDP User datagram protocol
Is connectionless, there is not a process of creating a connection session between hosts.
Doesn't have flow control because there is no session between them, the sender decides the speed of the packets instead of the receiver.
It is not reliable because we are sending packets without any acknowledgement, we dont know if the receiver got the packets and the receiver cant tell the sender to send back missing packets.
It is used in video games, streaming.

Speedy delivery
So we placed the packets inside the truck, we need to give this truck a destination address, which means a destination ip address. After the truck takes it to the destination (We can think of it as a house), it needs to kno which room in the house the packet needs to be placed into. The kitchen, bedroom,living room.. which one? 
We can think that these rooms have a port number, and remember that the packets had the tcp and udp protocols? These protocols help us know which port to deliver the packet to.
So the truck has a source ip, house is a destination ip, packets have either tcp or udp protocol and the destination port is written on it.

Lots of ports
an ipv4 socket consists of ip address,the protocol used (tcp or udp) and the port number
on server side it is;
server ip address, protocol, server application port number
on client side;
client ip address, protocol, client port number
the well known ports or permanent ports are
from 0 to 1023
the ephemeral ports are from 
1024 to 65,535
We can actually use any port we desire while connecting to a server, also servers can use any port they want too.
We just use the well known ports to have an understanding of the protocols used like the ftp,http,https,ssh etc.

tcp and udp port number are between 0-65,535
most servers (services) use non-ephemeral/well known ports numbers.
80 fot http and 443 for https
when we are connecting to a web server our firewall expects it to be either port 80 or 443.
Port numbers are used for connection not security.
Also tcp port numbers are not the same as udp port numbers. A tcp port 80 is different than UDP port 80.

COMMON PORTS
FTP (File transfer protocol)
Used to transfer files between systems.
may use port tcp/20 or tcp/21.
port 20 is associated with the file transfer process itself.
port 21 is used to send control information.
Requires a username and password to enter.
You can list add delete.. files in it.

SSH (Secure shell)
uses port tcp/22.
Used to connect to a remote host using a console or terminal.
What we mean by secure is the data being sent and received is encrypted because we are using the internet to connect to the ssh.

SFTP (Secure file transfer protocol)
Uses port tcp/22 as well. Same with ssh.
This serves the same purpose with ftp, used to transfer files between systems but hats different is the process is encrypted.
Allows us to list add remove.. files, provides file system functionality.
The existence of this protocol means that ssh is not only used to gain remote access from a terminal, it may be used to securely transfer files too.

TELNET
Uses port tcp/23.
Same functionality as ssh but the difference is the connection is not encrypted and someone who is listening the internet traffic can look into our telnet packets sent and received to look into it, which is not encrypted. Everything is in the clear, which is why telnet is not commonly used in productions systems.

SMTP (Simple mail transfer protocol)
Used to exhange mails between mail servers.
uses ports tcp/25 or tcp/587.
On port 25 everything is in plaintext, in the clear.
On port 587 we use tls to encrypt the data being sent and received.
Also clients use other protocols to receive mails.
Such as IMAP or POP3.

DNS (Domain name system)
When we enter a fully qualified domain name (FQDN) like archlinux.org, dns converts that into the ip address of that domain which allows us to enter the website. We would need to memorize ip addresses of the website we want to visit to if dns wasn't a thing. Dns is so important and critical so we have more than one dns servers in production.
uses port udp/53.
port tcp/53 is used for large transfers between dns servers.
This port is used a lot in a internet traffic, if you listen to a traffic you are likely to see this port being used.

DHCP (Dynamic host configuration protocol)
When we connect to a wifi we are automatically assigned an ip address, the protocol we use for this is dhcp.
To use dhcp we need to have a dhcp server, usually our wifi router has a built in dhcp server but in enterprises we use it as a standalone server.
uses port udp/67 or udp/68.
We can also assign a static ip address to a device so that ip is reserved for that specific device.
There is also something called lease which is a duration of time for the ip we have, when the lease timer ends if we are still using the ip assigned to us we simply tell the dhcp server that we are still using it and then renew our lease. This is crucial because this allows us to free up unused ip addresses at the moment.

TFTP (Trivial file transfer protocol)
This protocol is used to transfer files too but the difference from ftp is it is used to transfer very small amount of files.
uses port udp/69.
There is only a read and write option, no filesystem structure.
Works with ethernet.
No authentication, no user or password needed.

http (Hyper text transfer protocol) or https (Hyper text transfer protocol secure)
http uses port tcp/80 and https uses port tcp/443.
We use these protocols when connecting to a web server.
They both have the same purpose but the difference is http doesnt have encryption so everything is in plaintext in our traffic, meanwhile https has ssl/tls encryption which makes it secure while transferring data to a webserver.

NTP (Network time protocol)
uses port udp/123.
Used to synchronize clock on network devices. This is important because it allows the devices to work together, for example the time and date is very important in the concept of logs, if our time is inaccurate in our device it might lead us to wrong conclusions.
It is an automatic protocol, devices sync their clock every hour or a specific time you set it to be.
It is also very accurate, greater than 1 milisecond on a local network.

SNMP (Simple network management protocol)
uses port udp/161.
We use this protocol to query and gather information and statistics about a network device.

v1 - The original;
Single query.
The data sent is plaintext.

v2-A good step ahead
You can make multiple queries at the same time and gather more information.
The data sent is still plaintext.

v3-A secure standard
Same as v2 but there is authentication, encryption and message integrity.

SNMP Traps
This function uses port udp/162, what this does is it scans for problems and sends it to the management station automatically without needing to make a query.

LDAP (Lightweight directory access protocol)
uses port tcp/389.
Used to access and store information in our network directories.
Hierarchy: Organization--organizational unit--common name
Everything we do is plaintext here.
We also have LDAPS which is secure, uses ssl.
It uses port tcp/636.

SMB (Server message block)
This is a built in windows protocol in file explorer, it is used for file and printer sharing.
uses port tcp/445.

SYSLOG
As you know logs are very important, syslog is a protocol where any network device can use it to send their logs to a syslog server. It doesnt matter which vendor it is from. Thats why its powerful. uses port udp/514.
It is also integrated into siem (Secruity information and event management)
Siem is used to analyze logs, it gathers logs in a single place, we can also filter these to look up for specific things. Siem also generates alerts when something suspicious happens. A powerful side of it is pattern recognition. It doesnt generate alerts when there is a single failed attempt at an account. But it generates alerts when multiple failed attempts to an account occurs.
It also automates incident response.
Also you need a lot of disk space to store these logs, more than you think.

MS-SQL 
uses port tcp/1433

RDP (Remote desktop protocol)
uses port tcp/3389
Used to share a desktop from a remote location.

SIP (Session initiation protocol)
uses port tcp/5060 or tcp/5061
it is used to set up voIP (Voice over IP) sessions
call ring play busy signal hang up

Other useful protocols
ICMP (İnternet control message protocol)
It is not used for transporting which means that it isnt using tcp or udp, this is a protocol on its own in the ip header. It is usually used to check in our network devices to see if they are connected and running. We can think of it as messaging someone "Hey are you up?" and they answer with yes or just dont answer at all.  If they do not answer this means they are not up. Icmp can also be used to check if a network is reachable. If a network isnt reachable it sends an "This network is not reachable" alert. Also when we use the ping command to ping an ip we are using the icmp protocol. It also give us an alert when ttl expires, just to let us know. Simply it tells us what is going on, are devices up and running? is ttl expired?

GRE (generic routing encapsulation)
It is used to create a tunnel between two endpoints, we create this tunnel generally when we use a vpn.
Also it is used to encapsulate information in an ip packet in the beginning of the tunnel and then decapsulate it at the end. Warning: This does not mean that our data is being encyrpyed. We need to use additional vpn protocols to encrypt our encapsulated data.

Site to site VPN
When two remote sites connect to each other, their connection goes through the internet.  For privacy reasons we use site to site vpn's which encrypts the data being sent over the internet.
The concentrators in this model are either routers or firewalls.
What concentrator does is it encrypts the data at the entrance of the tunnel and decrypts it and the end of it.

IPSEC (Internet protocol security)
Security for osi layer 3.
authenticates and encrypts every packet.
it is standardized which means firewalls with different vendors can still connect to each other to make a tunnel. Provides confidentiality by encrypting data and integrity by using digital signatures.
There are two core ipsec protocols;
Authentication header (AH)
Encapsulation security payload (ESP)

IKE (Internet key exhange)
Both sides agree on encrypted/decrypted keys.
The keys are not sent across the internet.
A security association(SA) is created by doing this.
There are 2 phases,
Phase 1;
2 shared secret keys are created using the diffie-hellman algorithm
ISAKMP (İnternet security association and key management protocol) is used for this,it is a channel for the tunnels in the phase 2.
uses port udp/500, ESP goes inside it.

phase 2;
The two side agree on which cipher is going to be used and the sizes of the keys.
Also the inbound and outbound SA used for the ipsec tunnel.

Transport and tunnel mode
When we are creating our own ipsec, we are asked if we want to use tunnel or transport mode.
Transport Mode;
IP Header---IPSEC Headers---Data---IPSEC Trailers
As you can see, our data is encrypted withing the ipsec header and trailer, but the ip header is not encrypted which means someone who catches our packet can see the destination and source ip adress.

Tunnel Mode;
New IP Header---IPSEC Headers---IP Header---Data---IPSEC Trailers
As you can see we have a new ip header which is the destination of the ipsec concentrator, our original ip header is also encrypted alongside with our data.
Most ipsec's use this mode as it is more private and offers the highles level of encryption.

Authentication header (AH)
When we only use ah, we add a new ip header and a ah header to the data being sent, what ah does is it hashes the data so the integrity is ensured.

Network communication
Unicast
The communication is between only two hosts.
The data we sent goes to a single device.
One-to-one
The disadvantage of this is if we want to send data to multiple hosts we would need to establish a connection to every single of them one by one.
Web surfing, file transfers.
Ipv4 and ipv6

Multicast
One-to-many-of-many
The communication goes from one host to multiple hosts.
Used to send data to multiple hosts at the same time.
Hosts subscribe to your multicast address.
It could be a bad idea to do a multicast communication across another network or in a large network because it is a specialized protocol, your equipment needs to understand the protocol.
Uses ipv4 and ipv6
extensive ipv6

Anycast
One-to-one-of-many
used in ipv4 and ipv6
Packet is sent to the anycast address, it looks like a unicast address but it goes to the closes host available to us.

Broadcast
One-to-all
A packet is sent to everyone on the network.
used in ipv4, no ipv6.
Arp request.

Wireless standards
When we connect to a wifi with our wireless device we are using the IEEE 802.11 standards.
IEEE (Institue of electrical and electronics engineering)
We constantly need to check up on changes in these standards because it is constantly getting updated and changed.
The wireless network standards now have a more marketable name, they are easier to understand.
For example we now refer to 802.11ax as wifi 6.
Also there is a wifi trademark which show that the device is wifi alliance tested.

LTE (Long term evolution)
Can be referred as 4G.
When we are using our mobile phone or mobile tablet, we are using the network provided by our wireless provider.
It is a convergence between the different standards of gsm and cdma came down to a single standard every provider can use.
Goes up to 150 Mbit/s downlaod speed.

LTE-A (Long term evolution advanced)
Goes up to 300 Mbit/s download speed.

5G Networking
Its  the fifth generation, came out in 2020 with a big impact on iot's, mobile networking and the cloud.
With the right configurations the speed can go up to 10 Gigabits/s with higher frequencies.
Slower speeds go from 100 Mbit/s to 900 Mbit/s.
Thanks to 5g, we can receive notifications faster, send data faster,have higher bandwidth levels, bandwith is not a big problem anymore and we can process more data in the cloud .

Satellite networking
When we are in an isolated environment where we cant access the internet, we use a satellite to connect to the internet via sending signals to the satellite outside at the earths orbit.
Unfortunately the bandwith is very low and the download rates are 100 Mbit/s down, 5 Mbit/s up. Also the cost of it is expensive.
It has high latency, 250ms up, 250ms down meaning half a second late.
There is a firm called starling which provides 40ms of latency and is now working to get it to 20ms.
Also there is something called line of sight, when something gets between us and the satellite at the earths orbit, our satellite can't get the signals so the performance goes down.
Also there is something we call rain fade when a thunderstorm occurs and our satellites signals get blocked.

Ethernet standards
It is the most popular network connection type used.
It is very common for your computer to have an ethernet port.
There are different types of ethernets with different cabling,connectors,speeds and equipment to connect those ethernet cables.
Also there are different standards for twisted pair copper and fiber optic cables.

IEEE Internet standards
Thanks to IEEE 802.3 standard, we can connect every device to the ethernet network.
Ethernet connection standards
1000-BASE-T--gigabit ethernet-copper-1 Gigabit per second
10G-BASE-T--gigabit ethernet-copper-10 Gigabit per second
1000-Base-SX--gigabit ethernet-fiber-1 gigabit per second

Optical fiber
Fiber communication
Fiber optic cables use light for transmission.
It doesn't get interrupted by radio frequencies unlike the twisted copper pair because there is no radio frequencies used.
It can transmit traffic over long distances compared to the copper wire because the  redundancy of signal is low.
It is nearly impossible to monitor the network because radio frequencies are not used.
There are two modes for it;
Single mode
can travel data up to 100 km's without regenerating the signal.
uses laser beam or a very intense led as a light source.
Has a small core which allows only a single mode.
Multi Mode
Can travel up to 2km, used for short ranges.
Has a bigger core than single mode fiber which allows multi modes.
An led is used for light source.

The importance of cable
Cables are used everywhere in networking.
Even if you mostly have wireless devices to connect to to the network, the switches, routers and access points still need a wire to connect.
Once a wire is installed to a device, it is very difficult to remove and change it so make sure that you are using the right cabling infrastructure.

Twisted pair copper cabling
This is the most used cable for connecting to the ethernet.
There are twisted pairs inside of it.  The pairs inside it arent twisted equally, some are tighter and some are looser. The stricter you twist it the less interference there is.
Also in these twisted pairs, we send a positive and an inversed signal called transmit + and transmit -. The reason we do this is to prevent electromagnetic interference and crosstalk.
When the signals in the cable pairs interfere each other its called crosstalk, also we have a near end cross talk (NEXT) which is measured at the start of the circuit.
Electromagnetic interference is for example we have a twisted pair copper connected to a pc sending signals and we put and use a microwave next to it, when we do this there is a electromagnetic interference which bleeds into the wire and corrupts the data.

Speed
Cables dont have a speed, the copper is just sitting in there.
What cables do is they support a signal which it allows us to send a certain amount of data specificed by the 802.3 IEEE standard. The amount of data that can be transferred changes depending on the ethernet standard you are using.

Coaxial cable
Two or more forms share a common axis
RG-6 is used in television/digital cable

Network topologies
It describes how different networks are connected to each other.
This is useful in the planning process of building a network and also in the troubleshooting process in a way that we can see how the network is sending data to another network and what type of topology it is

Star/Hub and spoke
One of the most used topologies in enterprise networks.
Every device is connected to a central device, a switch.

Mesh
It is a topology where your data goes through multiple network links to reach the destination.
We can also use these links for load balancing.
The reason that there are multiple links is that if one link fails or goes down, we can use the other links to send our data, there isnt a single way to send data in this topology, there are alternatives.
Usually used in WAN's.
There are two types;
Full Mesh: Every device is connectedto every other device directly which makes it extremely expensive to build and complex cabling with redundancy.
Partial Mesh: Some devices have multiple connections, not all. Which makes cabling simpler while also the redundancy and the cost gets balanced.

Hybrid
It's a topology created using different types of topologies.
For example we might have a star, point to point and a mesh topology in our enterprise.
When we combine all of these together we get ourselves a hybrid topology.

Spine and leaf
This architecture consists of switches, the leaf's are connected to spines and spines are connected to leafs, but spines are not connected to each other and the leafs are not connected to each other.
There is also something called top of rack switching.
Every physical rack in our data center has a physical switch on top of it, we connect our servers or devices to these switches on top of the rack. By doing this we connect our devices to others easier,you get simpler cabling, it is redundant and also faster.
The downside is if you have a lot of racks in your data center you might need to get additional switches which are expensive.

Point to point
One-to-one connection.
Used to connect to WAN's.
It was very popular back then used in older WAN links called point-to-point T1.
You can use it to connect one building to another in a campus.

Three-tier architecture
Most enterprises use this architecture in their building.
Core;
It's the center of our network.
Our databases, servers, applications rest here.
End devices need connection to these.
Distribution;
This is where our switches are. This layer is the bridge between our servers and the end devices, it creates a connection between them.
Access;
Access switches for connecting our end devices to the distribution layer are in this layer.

Collapsed core
Used in small companies.
Easier and cheaper to implement than the three tier architecture.
The core and distribution layers are combined and collapsed.
Less switches, lower cost and less cabling.
The access layer is still the same which end devices connecting to switches next to them.
Not as resilliant as the three tier architecture.

Traffic flows
In a datacenter, it is important to know where the data goes to and comes from.
East-West;
Is the data flowing inside the data center from one device to another.
It has low latency.
Nort-South;
It's the data coming from or going to an external source.
We have more security measures against this data flow since we dont really know who the source is.

IPV4 addressing
Reserved addresses: 240.0.0.1-240.255.255.254
Any that is a class 'E' address is a reserved address.
Loopback Addresses:  127.0.0.1-127.255.255.254
VIP(Virtual ip address)
Not associated with a physical network adapter.
Examples are virtual machines and internal routers.

APIPA(Automatic private ip addressing)
When we dont have a dhcp server on our network, this guy assigns us an ip called link-local address. But it is not as capable as the dhcp protocol.
When we are assigned a link-local address, we can only communicate with the devices on our local network, we cant access the internet or the devices outside of our subnet.
Also ietf reserved 169.254.0.1 through 169.254.255.254.
first and last 256 ip addresses are reserved and not assigned to end stations.
functional block of 169.254.1.0 through 169.254.254.255.
Just like dhcp, apipa also has an automatic process for assigning ip's.
It uses the arp protocol to do so.
It asks the subnet if a particular ip is used, and if no one answers that ip is assigned that is between the functional block.
![[Pasted image 20260529104943.png]]
Classful Subnetting
Not used since 1993.
But still used in conversations when talking about ip's and subnets.
Can be a starting point when subnetting.
![[Pasted image 20260529110402.png]]

Classless Subnetting
CIDR(Classless inter domain routing)
Created around 1993, still used.
Removed the restrictions caused by the classful subnet masks.
"CIDR" block notation.
Instead of referring to the subnet masks as decimals we refer to it's binary.
For example 192.168.1.12/24.
/24 is CIDR here.

Why subnet the network?
Because it is functionally impossible for a single device to know each devices location in the world, so thats why we create smaller networks with routers inside it, we simply send our packet to the router and they do the job, we dont have to know the exact location of the destination thanks to this.

To create small networks we use VLSM (Variable length subnet masks)
VLSM(Variable length subnet mask)
As you know, classful subnet masks are inefficient, so we use vlsm!
Instead of having a fixed subnet class like class A subnet mask 255.0.0.0,
we can configure it however we like!
For example we can do 255.224.0.0 depending on how much network we need and how much hosts are going to be in the network.
We can also use different subnet masks in the same classful network.

SDN (Software defined networking)
Virtualizing the functions of the physical network devices so we can deploy them anytime and anywhere with the amount that we need. It's used to create virtual networks in an environment.
These functions are data, control and management planes.

Data plane
This is the function that does the heavylifting, its job is to forward,encrypt,trunk and nat the data.
Control plane
This is the function that has routing tables.
It controls where the data goes and manages where the data goes.
Management plane
In this function we do the management of the device.
Ssh,api

DCI (Data center interconnection)
Used to connect data centers to each other seamlessly, the geographic location doesnt matter.
Isp customers use data centers all around the world and  we can use this to connect them to one core network.
Of course, the cloud is used to distribute applications to different data centers.
These applications can move from one to another data center at any time.

Zero trust
Every device in a network is untrusted and must be verified.
The reason is that when someone or an attacker accesses and enters the network it is literally open and they can access anywhere but with zero trust we dont allow that. Even if they enter the network they aren't trusted.
MFA, encryption decryption, firewalls can be used.

SASE (Secure access service edge)
Next gen virtual private network for users to securely connect to the enterprise network. For example our cloud.