# Understanding The OSI Model 1.1
## The OSI Model
- What is the OSI Model
	- Open Systems Interconnection Reference Model
- It's a guide. Not strict
- This is not the OSI Protocol Suit
	- Most OSI Protocols didn't catch on
- There are unique protocols at every layer
- You'll refer to this model for the rest of your career
- Layers: **All People Seem To Need Data Processing**
	- 7: Application
	- 6: Presentation
	- 5: Session
	- 4: Transport
	- 3: Network
	- 2: Data Link
	- 1: Physical
## Layer 1 - The Physical Layer
- Physics of the network
	- Signaling, cabling, connectors
	- This layer isn't about protocols
- Physical Layer Problems
	- Fix your cabling, punch downs, etc
	- Run loopback tests, test/replace cables, swap adapter cards
## Layer 2 - Data Link Later
- The basic network language
	- Foundation of communication at the data link layter
- Data Link Control (DLC) protocols
	- MAC (Media Access Control) address on Ethernet
- The "Switching" layer

## Layer 3 - Network Layer
- The "Routing" layer
- Internet Protocol (IP)
- Fragments frame to traverse different networks

## Layer 4 - Transport Layer
- "Post Office Layer"
	- Parcels and letters
- TCP (Transmission Control Protocol) and UDP (User Datagram Protocol)

## Layer 5 - Session Layer
- Communication Management between devices
	- Stop, start, reset
- Controls protocols, tunneling protocols

## Layer 6 - Presentation Layer
- Character encoding
- Application encryption
- Often combined with the application Layer
## Layer 7 - Application Layer
- Layer we see
- HTTP, FTP, DNS, POP3

## Real World to OSI Model
- Physycal
	- Cables, fiber, the signal itself
	- Electrical Signals
- Data Link
	- Frame, MAC address, Extended Unique Identifier (EUI-48, EUI-64), Switch
	- Ethernet
- Network
	- IP Address, Router, Packet
	- IP Encapsulation
- Transport
	- TCP Segment, UDP datagram
	- TCP encapsulation
- Session
	- Control Protocols, tunneling protocols
	- Link presentaton to the transport
- Presentation
	- Application Encryption (SSL/TLS)
	- SSL Encryption
- Application
	- Your eyes
	- https://mail.google.com
- You can use wireshark to capture network data


# Networking Devices - 1.2
## Networking devices
- Many different ways to forward traffic
	- A data center full of equipment
- Every device has a purpose
	- The implementation may change over time
	- Once installed, it can often be difficult to remove
- There are new technologies all the time
	- Always something to learn

## Router
- Routes traffic between IP subnets
	- OSI layer 3 device
	- Routers inside of switches sometimes called "Layer 3 switches"
		- Switches are usually a Layer 2 device
- Often connects diverse network types
	- LAN, WAN, copper, fiber, etc

## Switch
- Bridging done in hardware
	- Application specific integrated circuit (ASIC)
- An OSI Layer 2 device
	- Forwards traffic based on data link address
- Many ports and features
	- The core of an enterprise network
	- May provide Power over Ethernet (PoE)
- Multilayer switch
	- Includes Layer 3 (routing) functionality
## Firewalls
- Filter traffic by port number or application
	- Traditional vs. NGFW
- Encrypt traffic
	- VPN between sites
- Most firewallls can be layer 3 devices (routers)
	- Often sits on the ingress/egress of the network
	- Network Address Translation (NAT)
	- Dynamic routing
## IDS and IPS
- Intrusion Detection System/Intrusion Prevention System
	- Watch network traffic
- Intrusions
	- Exploits against operating systems, applications, etc.
	- Buffer overflows, cross site scripting, other vulnerabilities
- Detetion vs. Prevention
	- Detect - Alarm or alert
	- Prevent - Stop it before it gets to the network
## Balancing the Load
- Distribute the load
	- Multiple servers
	- Invisible to the end user
- Large scale implementations
	- Web server farms, database farms
- Fault tolerance
	- Server outages have no effect
	- Very fast convergence
## Load balancer
- Configurable Load
	- Manage across servers
- TCP Offload
	- Protocol overhead
- SSL Offload
	- Encryption/Decryption
- Caching
	- Fast Response
- Prioritization
	- QoS
- Content Switching
	- Application centric balancing
## Proxies
- Sits between the users and the external networks
- Receives the user requests and sends the requests on their behalf (the proxy)
- Useful for cahing information, access control, URL filtering, content scanning
- Applications may need to know how to use the proxy (explicit)
- Some proxies are invi8sible (transparent)

## NAS vs SAN
- Network Attached Storage (NAS)
	- Connect to a shared storage device across the network
	- File level access
- Storage Area Network (SAN)
	- Looks and feels like a local storage device.
		- Block level access
	- Very efficient reading and writing
- Requires a lot of bandwidth
	- May use an isolated network and high speed network technologies
## Access Point (AP)
- Not a wireless router
	- A wireless router is a router and an access point in a single device
- An access point is a bridge
	- Extends the wired network onto the wireless network
	- OSI layer 2 device
## Wireless networks everywhere
- Wireless networking is pervasive
	- And you don't usually have just a single access point
- Your access points may not even be in the same building
	- One or more at every remote site
- Configurations may change at any moment
	- Access policy, security policies, AP configs
- The network should be invisible to your users
	- Seamless network access, regardless of role
## Wireless LAN controllers
- Centralized management of access points
	- A single "Pane of glass"
- Deploy new access ponts
- Performance and security monitoring
- Configure and deploy changes to all sites
- Report on access point use
- Usually a proprietary system
	- The wireless controller is paired with the access points

# Networking Functions - 1.2
## Networking Functions
- A lot is happening behind the scenes
	- Many networking functions are part of the infrastructure
- Access to important data from anywhere in the world
- Remote access
	- Secure network communication
- Traffic management
	- Prioritizes the important applications
- Protocol support
	- Maintain uptime and availability

## Content Delivery Network (CDN)
- It takes time to get data from one place to the other
	- Speed up the process
- Geographically distributed caching servers
	- Duplicate the data
	- Users get the data from a local server
- You are using CDN right now
	- Used on many websites
	- Invisible to the end user

## VPN (Virtual Private Network)
- Secure private data traversing a public network
	- Encrypted communication on an insecure medium
- Concentrator / head-end
	- Encryption/decryption access device
	- Often integrated into a firewall
- Many deployment options
	- Specialized cryptographic hardware
	- Software based options available
- Often used with client software
	- Sometimes built into the OS

## Quality of Service (QoS)
- Traffic shaping, packet shaping
- Control by bandwidth usage or data rates
- Set important applications to have higher priorities than other apps
- Manage the QoS
	- Routers, switches, firewalls, QoS devices, etc
## Time to Live (TTL)
- How long should data be available?
	- Not all systems or protocols are self regulating
	- We sometimes need to tell a system when to stop
- Create a timer
	- Wait until traversing a number of hops, or wait until a certain amount of time elapses
	- Then either stop or drop
- Many different uses
	- Drop a packet caught in a loop
	- Clear a cache
## Routing loops
- Router A things the next hop is Router B. Router B thinks the next hop is Router A. They get stuck.
- Easy to misconfigure, especially with static routing
- TTL is used to stop the loop
## IP (Internet Protocol)
- Loops could cause a packet to live forever
	- Drop the packet after a certain number of hops
- Each pass through a router is a hop
	- Default TTL for macOS/Linux is 64 hops
	- Defaukt TTL for Windows is 128 hops
- The router decreases TTL by 1
	- A TTL of 0 is dropped by the router
## DNS (Domain Name System)
- DNS Lookup
	- Resolve an IP address from a fully qualified Domain Name
	-  [WEBSITE NAME] = [IP ADDRESS]
- A device caches the lookup for a certain amnount of time
	- How long? TTL seconds long
	
# Designing the Cloud - 1.3
## Designing the cloud
- On demand computing power
	- Click a button
- Elasticity
	- Scale up or down as needed
- Applications also scale
	- Scalability for large implementations
	- Access from anywhere
- Multitenancy
	- Many different clients are using the same cloud infrastructure
## Virtual networks
- Server farm with 100 individual computers
- All servers are connected with enterprise switches and routers
	- With redundancy
- Migrate 100 physical servers to one physical server
	- With 100 virtual servers inside
- What happens to the network?
## Network Function Virtualization (NFV)
- Replace physical network devices with virtual versions
	- Manage fromt he hypervisor
- Same functionality as a physical device
	- Routing, switching, load balancing, firewalls, etc
- Quickly and easily deploy network functions
	- Click and deply from the hypervisor
- Many different deployment options
	- Virtual machine, container, fault tolerance, etc
## Connecting to the cloud
- A virtual private cloud (VPC)
	- A pool of resources created in a public cloud
- Common to create many VPCs
	- Many different application clouds
- Connect VPCs with a transit gateway
	- And users to VPCs
	- A "cloud router"
- Now make is secure
	- VPCs are commonly on different IP subnets
	- Connecting to the cloud is often through a VPN

## Virtual Private Cloud Endpoints

![[Pasted image 20260518091330.png]]
![[Pasted image 20260518091427.png]]
## Security groups and lists
- A firewall for the cloud
	- Control inbound and outbound traffic flows
- Layer 4 port number
	- TCP or UDP port
- Layer 3 address
	- Individual addresses
	- CIDR block notation
	- IPv4 or IPv6
## Network Security List
- Assign a security rule to an entire IP subnet
	- Applies to all devices in the subnet
- Very broad
	- Can become difficult to manage
	- Not all devices in a subnet have the same security posture
- More granularity may be needed
	- Broad rules may not provide the right level of security
## Network Security Group
- Assign a security rule to a specific NIC (VNIC)
	- Applies to specific devices and network connections
- More granular than network security lists
	- Different rules for devices in the same IP subnet
- Better control and granularity
	- The best practice for cloud security rules


# Cloud Models : 1.3
## Cloud Deployment
- Public
	- Available to everyone over the internet
- Private
	- Your own virtualized local data center
- Hybrid
	- A mix of public and private
## Software as a Service (SaaS)
- On demand software
	- No local installation
	- Why manage your own email distribution or payroll?
- Central management of data and applications
	- - Your data is out there
- A complete application offering
	- No development work required
	- Google Mail, Office 365
## Infrastructure as a service (IaaS)
- Sometimes called Hardware as a Service (HaaS)
	- Outsource your equipment
- You're still responsible for the management
	- And for the security
- Your data is out there, but more within your control
- Web server providers
## Platform as a Service (PaaS)
- No servers, no software, no maintenance team, no HVAC
	- Someone else handles the platform, you handle the development
- You don't have direct control of the data, people, or infrastructure
	- Trained security professionals are watching your stuff
	- Choose carefully
- Put the building blocks together
	- Develop your app from what's available on the platform
	- Salesfoce, etc
## Cloud Responsibility Matrix

![[Pasted image 20260519060914.png]]

# Introduction to IP
## A series of moving vans analogy
- Efficiently move a large amounts of data
	- Using a shipping truck
- The network topology is the road
	- Ethernet, DSL, cable system
- The truck is the Internet Protocol (IP)
	- We've designed roads for this truck
- The boxes hold your data
	- Boxes of TCP and UDP
- Inside the boxes are more things
	- Application Information

## IP - Internet Protocol

![[Pasted image 20260519061226.png]]
## TCP and UDP
- Transported inside of IP
	- Encapsulated by the IP protocol
- Two ways to move data from place to place
	- Different features for different applications
- OSI Layer 4
	- The transport layer
- Multiplexing
	- Use many different applications at the same time
	- TCP and UDP
## TCP - Transmission Control Protocol
- Connection oriented
	- A formal connection setup and close
- "Reliable" delivery
	- Recovery from errors
	- Can manage out of order messages or retransmissions
- Flow control
	- The receiver can manage how much data is sent

![[Pasted image 20260519061551.png]]

## UDP - User Datagram Protocol
- Connectionless
	- No formal open or close to the connection
- "Unreliable" delivery
	- No error recovery
	- No reordering of data or retransmission
- No flow control
	- Sender determines the amount of data transmitted
![[Pasted image 20260519061802.png]]
## Speedy delivery
- The IP delivery truck delivers from one IP address to another IP address
	- Every house has an address, every computer has an IP address
- Boxes arrive at the house / IP address
	- Where do the boxes go?
	- Each box has a room name
- Port is written on the outside of the box
	- Drop the box into the right room
## Lots of ports
- IPv4 sockets
	- Server IP address, protocol, server application port number
	- Client IP address, protocol, client port number
- Non ephemeral ports - permanent port numbers
	- Ports 0 through 1023
	- Usually on a server or service
- Ephemeral ports- temporary port numbers
	- Ports 1034 through 65,535
## Ports on the network
- Web server - tcp/80
- VoIP server - udp/5004
- Email server - tcp/143

![[Pasted image 20260519062219.png]]
![[Pasted image 20260519062312.png]]
# Common Ports: 1.4
## FTP - File Transfer Protocol
- tcp/20 (active mode data), tcp/21 (control)
	- Authenticates with a username and password
- Transfers files between systems
	- Generic file transfer method
	- Not specific to an OS
- Full featured funtionality
	- List, add, delete, etc
## SSH - Secure Shell
- tcp/22
- Text based console communication
- Encrypted communication link
## SFTP - Secure FTP
- tcp/22
	- Uses the SSH File transfer protocol
- Generic File transfer with security
	- Encrypted network communication
- Provides file system funtionality
	- Resuming interrupted transfers, directory listings, remote file removal
- Uses SSH (port 22)
	- SSH isn't just for console communication
## Telnet
- Telnet - Telecommunication Network
- tcp/23
- Console access
	- Similar functionality to SSH
- In the clear communication
	- Not the best choice for production systems
## SMTP - Simple Mail Transfer Protocol
- Server to server email transfer
	- tcp/25 (SMTP using plaintext)
	- tcp/587 (SMTP using TLS encryption)
- Also used to send mail from a device to a mail server
	- Commonly configured on mobile devices and email clients
- Other protocols are used for clients to receive email
	- IMAP, POP3
## DNS - Domain Name System
- udp/53
	- Converts names to IP addresses
	- Large transfers may use tcp/53
- These are very critical resources
	- Usually multiple DNS servers are in production
## DHCP - Dynamic Host Configuration Protocol
- udp/67, udp/68
- Automated configuration of IP address, subnet mask, and other options
	- Requires a DHCP server
	- Server, appliance, integrated into a SOHO router, etc
- Dynamic/Pooled
	- IP addresses are assigned in real time from a pool
	- Each system is given a lease, must renew at set intervals
- DHCP reservation
	- Addresses are assigned by MAC address in the DHCP server
	- Quickly manage addresses from one location
## TFTP - Trivial File Transfer Protocol
- udp/69
- VEry simple file transfer appication
	- Read and write files
- No authentication
	- Not used on highly secure systems
- Useful when starting a system
	- Transfer configuration files
	- Quick and easy
## HTTP and HTTPs
- Hypertext Transfer Protocol
	- Communication in the browser
	- And by all other applications
- In the clear or encrypted
	- SSL (Secure Sockets Layer) or TLS (Transport Layer Security)
- HTTP
	- tcp/80
	- Hypertext Transfer Protocol
	- Web server communication
- HHTPS
	- tcp/443
	- HTTP over TLS or SSL
	- Web server communication with encryption
## NTP - Network Time Protocol
- Switches, routers, firewalls, servers, workstations
	- every device has its own clock
- udp/123
- Synchronizing the clocks becomes critical
	- Log files, authentication information, outage details
- Automatic updates
- Flexible - You control how clocks are updated
- Very accurate
	- Accuracy is better than 1 millisecond on a local network
## SNMP - Simple Network Management Protocol
- Gather statistics from network devices
- udp/161
- v1 - The original
	- Structured tables
	- In the clear
- v2 - a good step ahead
	- Data type enhancements
	- Bulk transfers
	- Still in the clear
- v3 - A secure standard
	- Message integrity
	- Authentication
	- Encryption
- SNMP traps
	- udp/162
	- Alerts and notifications from the network device
## LDAP/LDAPS
- LDAP (Lightweight Directory Access Protocol)
	- tcp/389
	- Store and retrieve information in a network directory
- LDAPS (LDAP Secure)
	- A non standard implementaton of LDAP over SSL
	- tcp/636
## SMB - Server Message Block
- Protocol used by Microsoft Windows
	- File sharing, printer sharing
	- Also called CIFS (Common Internet File System)
- Integrated into the operating system
	- Access rights integration across systems
	- File share publishing
	- File locking
- Direct over tcp/445 (NetBIOS-less)
	- Direct SMB communication over TCP
## Syslog
- Udp/514
- Standard for message logging
	- Diverse systems, consolidated log
- Usually a central log collector
	- Integrated into the SIEM
		- Security Information and Event Manager
- You're going to need a lot of disk space
	- Data storage from many devices over an extended timeframe
## Databases
- Collection of information
	- Many different types of data
	- One common method to store and query
- Structured Query Langiage (SQL)
	- A standard language across database servers
- Microsoft SQL Server
	- MS-SQL
	- tcp/1433
## Remote Desktop Protocol
- tcp/3389
- Share a desktop from a remote location
	- Connect to an entire desktop or just an application
- Remote Desktop Services on many windows versions
	- Clients for Windows, macOS, Linux, Unic, iPhone, and others
## SIP - Session Initiation Protocol
- Voice over IP (VoIP) signaling
	- tcp/5060 and tcp/5061
- Setup and manage VoIP sessions
	- Call, ring, play busy signal, hang up
- Extended voice communication
	- Video conferencing
	- Instant messaging
	- File transfer
	- etc

# Other Useful Protocols - 1.4
## ICMP
- Internet Control Message Protocol
	- "Text messaging" for your network devices
- Another protocol carried by IP
	- Not used for data transfer
- Devices can request and reply to administrative requests
	- Hey are you there? / Yeah I'm here
- Devices can send messages when things don't go well
	- That network you're trying to reach is not reachable from here
	- Your time to live expired, just letting you know
## GRE
- Generic Routing Encapsulation
	- The "tunnel" between two endpoints
- Encapsulate traffic inside of IP
	- Two endpoints appear to be directly connected to each other
	- No built in encryption
![[Pasted image 20260520060901.png]]
## VPN
- Virtual Private Networks
	- Encrypted (private) data traversing a public network
- Concentrator
	- Encryption/decryption access device
	- Often integrated into a firewall
- Many deployment options
	- Specialized cryptographic hardware
	- Software based options available

## Site to Site VPN
- Always on or almost always on
- Firewalls often act as VPN concentrators
	- Probably already have firewalls in place

![[Pasted image 20260520061139.png]]

## IPSec (Internet Protocol Security)
- Security for OSI Layer 3
	- Authentication and encryption for every packet
- Confidentiality and integrity/anti-replay
	- Encryption and packet signing
- Very standardized
	- Common to use multi vendor implementations
- Two core IPSec protocols
	- Authentication Header (AH)
	- Encapsulation Security Payload (ESP)

## Internet Key Exchange
- Agree on encryption/decryption keys
	- Without sending the key across the network
	- Builds a Security Association (SA)
- Phase I
	- Use Diffie-Helman to create a secret shared key
	- udp/500
	- ISAKMP (Internet Security Association and Key Management Protocol)
- Phase II
	- Coordinate ciphers and key sizes
	- Negotiate an inbound and outbound SA for IPsec
![[Pasted image 20260520061645.png]]

## Transport mode and Tunnel Mode
- Original packet
	- IP Header and Data
- Transport Mode
	- IP Header
	- IPsec Headers
	- Data
	- IPsec Trailers
- Tunnel Mode
	- New IP Head Header
	- IPsec Header
	- IP header
	- Data
	- IPsec Trailers
## Authentication Header
- Hash of the packet and shared key
	- MD5, SHA-1, or SHA-2 are common
	- Adds the AG to the packet header

![[Pasted image 20260520061950.png]]
## Encapsulation Security Payload (ESP)
- Encrypts the packet
	- MD5, SHA-1, or SHA-2 for hash, and 3DES or AES for encyption
	- Adds a header, a trailer, and an Integrity Check Value

![[Pasted image 20260520062130.png]]

# Network Communication - 1.4
## Unicast
- One station sending information to another
	- One to one
- Send information between two systems
- Web surfing, file transfers
- Does not scale optimally for real time straming media
- IPv4 and IPv6
## Multicast
- Delivery of information to interested systems
	- One to many of many
- Multimedia delivery, stock exchanges, dynamic routing updates
- Very specialized
	- Difficult to scale across large networks
- Used in both IPv4 and IPv6
	- Extensive use in IPv6
## Anycast
- Single destination IP that has multiple paths or two or more endpoints
	- One to one of many
	- Used in IPv4 and IPv6
- Configure the same anycast address on different devices
	- Looks like any other unicast address
- Packets sent to an anycast address are delivered to the closest interface
	- Announce the same rout out of multiple data centers, clients use the data center closes to them
	- Anycast DNS
## Broadcast
- Send information toe everyone at once
	- One to all
- One packet, received by everyone
- The broadcast domain has a limited scope
- Routing updates, ARP requests
- Used in IPv4
- Not used in IPv6, multicast is used instead

# Wireless Networking - 1.5
## Wireless standards
- Wireless networking (802.11)
	- Managed by the IEE LAN/MAN standards committee (IEEE 802)
	- Institute of Electrical and Electronic Engineers
- Many updates over time
	- Check with IEEE for the latest
- The WIFI trademark
	- WiFi Alliance handles interoperability testing
- Modern standards have more marketable names
	- 802.11ax = Wifi 6

## 802.11 networking
- 802.11a
	- 5 GHz
	- 6-54 Mbit/s
- 802.11b
	- 2.4 GHz
	- 1-11 Mbit/s
- 802.11g
	- 2.4 GHz
	- 6-54 Mbit/s
- 802.11n
	- Wifi 4
	- 2.4/5 GHz
	- 72-600 Mbit/s
- 802.11ac
	- Wifi 5
	- 5 GHz
	- 433-6933 Mbit/s
- 802.11ax
	- Wifi 6 and 6E
	- 2.4/5/6 Ghz
	- 574-9608 Mbit/s
- 802.11be
	- Wifi 7
	- 2.4 GHz/5GHz/6Ghz
	- 1376-46,120 Mbit/s
## 4g and LTE
- Long Term Evolution (LTE)
	- A 4g technology
	- Converged standard (GSM and CDMA providers)
	- Based on GSM and EDGE (Enhanced Data Rates for GSM Evolution)
	- Standard Supports download rates of 150 Mbit/s
- LTE Advanced (LTE-A)
	- Standard supports download rates of 300 Mbit/s

## 5g
- Fifth generation cellular networking
	- Launched worldwide in 2020
- Significant performance improvements
	- At higher frequencies
	- Eventually 10 gigabits per second
	- Slower speeds from 100-900 Mbit/s
- Significant IoT impact
	- Bandwidth becomes less o f a constraint
	- Larger data transfers
	- Faster monitoring and notification 
	- Additional cloud processing
## Satellite Networking
- Communication to a satellite
	- Non terrestiral communication
- High cost relative to terrestrual networking
	- 100 Mbit/s down, 5 Mbit/s up are common
	- Remote sites, difficult to network sites
- Relatively high latency
	- 250 ms up, 250 ms down
	- Starlink advertises 40 ms and is working on 20 ms
- High frequencies - 2 Ghz
	- Line of sight, rain fade

# Ethernet Standards - 1.5
## Ethernet
- The most popular networking technology in the world
	- Standard, common, nearly universal
- Many different types of ethernet
	- Speeds, cabling, connectors, equipment
- Modern Ethernet uses twisted pair copper or fiber
	- The standard defines the media

## IEEE Ethernet standards
- The IEEE 802.3 committee
	- Institute of Electrical and Electronic Engineers
	- All types and standards of Ethernet
	- Copper and fiber
- IEEE Standards for Internet
	- 1000BASE-T: Gigabit ethernet, copper, 1 gigabit per second
	- 10GBASE-T: 10 Gigabit Ethernet, copper, 10 gigabits per second
	- 1000BASE-SX: Gigabit Ethernet, fiber, 1 gigabit per second

## Deciphering the standard
- Speed, signal, and media
	- All contained in the standard name, i.e, 1000BASE-T
- The number is related to the network Speed
	- 1000 is commonly 1,000 megabits per second (or one gigabit per/sec)
	- 10G would be 10 gigabits per second
- BASE (baseband)
	- Single frequency using the entire medium
	- Broadband uses many frequencies, sharing the medium
- Media Type
	- T is twisted pair copper, F is fiber
	- SW is short wavelength light
# Optical Fiber - 1.5
## FIber Communication
- Transmission by light
	- The visible spectrum
- No RF signal
	- Very difficult to monitor or tap
- Signal slow to degrase
	- Transmission over long distances
- Immune to radio interference
	- There's no RF

## Fiber Optic Diagrams
![[Pasted image 20260521061634.png]]
![[Pasted image 20260521061700.png]]
![[Pasted image 20260521061720.png]]

## Multimode Fiber
- Short range communication
	- Up to 2 km
- Inexpensive light source
	- ie, LED
![[Pasted image 20260521061816.png]]

## Single Mode Fiber
- Long range communications
	- Up to 100 km without processing
- Expensive light source
	- Laser beams
![[Pasted image 20260521061901.png]]

# Copper Cabling - 1.5
## The importance of cable
- Fundamental to network communication
	- Incredibly important foundation
- Usually only get one good opportunity at building your cabling infrastructure, so make it good
- The cast majority of wireless communication uses cables
	- Everything eventually touches a cable
## Twisted pair copper cabling
- Balanced pair operation
	- Two wires, with equal and opposite signals
	- Transmit+, Transmit-/Receive+, Receive-
- The twist is the secret
	- Twisted cables keep a single wire constantly mioving away from interference
	- The opposite signals are compared on the other end
- Pairs in the same cable have different twists rates
## Cable speeds
- Cables don't have a speed
	- The copper just sits there
- Electric signals are sent over copper cable
	- The signal encoding determined the data transfer rate
- A cable must be manufactured to specific standards
	- IEEE 802.3 Ethernet standards determine the cable type
- Cable standars are descried as a "category" of cable
	- Category 6, category 7, etc
	- Check for the IEEE standard to determine the minimum cable category
	- The minimum cable category for 1000BASE-T is Category 5

## Coaxial cables
- Two or more forms share a common axis
- RG-6 used in television/digital cable
	- And high speed internet over cable
![[Pasted image 20260521062513.png]]

## Twinaxial Cable
- Two inner conductors
	- Twinax
- Common on 10 Gigabit Ethernet SFP+ Cables
	- Full duplex
	- Five meters
	- Low cost
	- Low latency compared to twisted pair

## Plenum space
- Space between the drop ceiling and the actual ceiling
- Contains cables, heat sensors, and other pieces of infrastructure
## No Plenum
![[Pasted image 20260521062801.png]]

## Plenum
![[Pasted image 20260521062842.png]]
- Plenum Space
	- Building Air circulation
	- Heating and air conditioning system
- Concerns in the case of a fire
	- Smoke and toxic fumes
- Worst case planning
	- Important concerns for any structure
## Plenum rated cables
- Traditional cable jacket
	- Polyvinyl chloride (PVC)
- Fire rated cable jacket
	- Flourinated ethylene polymer (FEP) or low smoke polyvinyl chloride (PVC)
- Plenum rated cable may not be as flexible
	- May not have the same bend radius
- Worst case planning
	- Used in plenum and risers
	- Important concerns for any structure

# Network Transceivers - 1.5
## Transceiver
- Transmitter and receiver
	- Usually in a single component
- Provides a modular interface
	- Add the transceiver that matches your network
- Many different types
	- Ethernet or Fibre Channel
	- Not compatible with each other
- Different media types
	- Fiber and copper
## SFP and SFP+
- Small Form Factor Pluggable (SFP)
	- Commonly used to provice 1Gbit/s fiber 
	- 1 Gbit/s RJ45 SFPs also available
- Enhanced Small Form Factor Pluggable (SFP+)
	- Exactly the same physical size as SFPs
	- Supports data rates up to 16 Gbit/s
	- Common with 10 Gigabit Ethernet

## QSFP
- Quad Form Factor Pluggavle
	- 4 channel SFP = Four Gbit/s = 4 Gbit/s
	- QSFP_ is 4 channel SPF+ = Four 10 Gibit/sec = 40 Gbit/sec
- Combine four SFPs into a single transceiver
	- Cost savings in fiber and equipment
## Transceiver Comparison
![[Pasted image 20260523063640.png]]

# Fiber Connectors 1.5
## SC - Subscriber Connector
- Not the actual name, we just made something up
	- Square Connector and Standard Connector also acceptable
- Pushes on to lock
	- Pull conntector to unlock
- A popular fiber connector
	- Common in many data centers

![[Pasted image 20260523063943.png]]

## LC - Local Connector
- Another popular fiber type
	- Smaller and more compact connector
- Locks in place with a clip
	- Press to release
- Other names:
	- Lucent Connector, Little Connector

![[Pasted image 20260523063918.png]]
## ST - Straight Tip
- Bayonet Connector
	- Stick and Twist
- Push on and turn
	- Locks in place
	- Turn to unlock
![[Pasted image 20260523064052.png]]
## MPO - Multi Fiber Push On
- Twelve fibers in a single connector
	- Save space and manage one cable
- Push to lock in place
	- Pull connector to unlock
- May also see the MTP abbreviation
	- A Corning Brand
	- The MTP MPO connector
![[Pasted image 20260523064225.png]]

![[Pasted image 20260523064239.png]]

# Copper Connectors 1.5
## RJ11 Connector
- Registered Jack type 11
	- 6 position, 2 conductor (62p2c)
- Telephone and DSL connection
![[Pasted image 20260523064411.png]]

## RJ45
- Registered Jack type 45
- 8 position, 8 conductor (8P8C)
	- Modular Connector
	- Ethernet
![[Pasted image 20260523064458.png]]
![[Pasted image 20260523064508.png]]
## F-Connector
- Coaxial Cable
	- Standard connector type
	- Threaded connector
- Cable television infrastructure
	- Cable modem
	- DOCSIS (Data Over Cable Service Interface Specification)
![[Pasted image 20260523064622.png]]

## BNC Connector
- Bayonet Neill-Concelman
	- Payle Neill (Bell Labs) and Carl Concelman (Amphernol)
	- Another common coaxial cable connector
		- Common with twinax and Ds3 WAN links
		- Video connections
	- Secure connections
		- Twist and lock in place

![[Pasted image 20260523064753.png]]
![[Pasted image 20260523064804.png]]
# Network Topologies: 1.6
## Network Topologies
- Useful in planning a new network
	- Physical layout of a building or campus
- Assists in understanding signal flow
	- Troubleshooting problems
## Star/Hub and Spoke
- Used in most large and small networks
- All devices are connected to a central device
- Switched Ethernet networks
	- The switch is in the middle
## Mesh
- Multiple links to the same place
	- Fully connected
	- Partially connected
- Redundancy, fault tolerance, load balancing
- Used in WANs.
	- Fully meshed and partially meshed
![[Pasted image 20260526060218.png]]

## Hybrid
- A combination of one or more physical topologies
	- Most networks are a hybrid

## Spine and leaf architecture
- Each leaf switch connects to each spine switch
	- Each spine switch connects to each leaf switch
- Leaf switches do not need to connect to each other. Same for spine switches
- Tope of rack switching
	- Each leaf is on the "top" of a phusical network rack
	- May include a group of physical racks
- Advantages
	- Simple cabling
	- Redundant
	- Fast
- Disadvantages
	- Additional switches may be costly
![[Pasted image 20260526060607.png]]

## Point to point
- One to one connection
- Older WAN links
	- "Point to point T-1"
- Connections between buildings
# Network Architectures: 1.6
## Three tier architecture
- Core
	- The center of the network
	- Web servers, databases, applications
	- Many people need access to this
- Distribution
	- A midpoint between the core and the users
	- Communication between access switches
	- Manage the path to the end users
- Access
	- Where the users connect
	- End stations, like printers
![[Pasted image 20260526061217.png]]

![[Pasted image 20260526061237.png]]

## Collapsed core
- Two tier model
	- Simplify the three tier architecture
	- A good fit for smaller organizations
- Combine Core and Distrubution layers
	- Collapse together
- Differences over three tier
	- Simpler to design and support
	- Less expensive to implement
	- Not as resilient
![[Pasted image 20260526061405.png]]
## Traffic flows
- Traffic flows within a data center
	- Important to know where traffic starts and ends
- East-West
	- Traffic between devices in the same data center
	- Relatively fast response times
- North-South traffic
	- Ingress/egress to an outside device
	- A different security posture than east-west traffic

![[Pasted image 20260526061625.png]]
# Binary Math: 1.7
## Basics of binary math
- A bit: A zero or one. Represents off or on
- A byte: Eight bits
	- Often called an "octet" to avoid ambiguity
- Binary decimal conversion: you add the numbers at each decimal place up

![[Pasted image 20260526061802.png]]
## Binary to decimal
- 0000 0010 = 2
- 1111 1111 = 255
- 154 = 1001 1010
## More bits, more addresses
- The more bits you have, the more addresses you can accommodate

## Extending the math
- Powers of two are useful for binary calculations and subnetting
![[Pasted image 20260526062204.png]]

# IPv4 addressing: 1.7

# Classful Subnetting: 1.7

# IPv4 Subnet Masks: 1.7
