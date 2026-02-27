# IT Basics

## Computer Hardware

##### Graphics Processing (GPU)
- For rendering parallel computing
#### Networking Equipment
- Router
- switches
- firewalls
- access points
- modems and gateways - device that connect networks to internet service providers  modems convert the signal from your ISP (cable , DSL fiber) in to a format usable by your network
Gateways often combine modem router and sometimes switch functionality into a single device that serves as the entry point to your network

component compatibility 

when building or upgrading system compatibility between components is crucial
- form factor considerations
- Interface compatibility - matching connection types to work together
- power requirements - 

#### System configuration and IT Fundamentals

- BIOS/UEFI - firmware interface that initializes hardware and boots the operating system
#### Network configuration

- IP addressing - static IP manually assigned , fixed network address
			 -  DHCP automatically assigned address from a center address
- DNS Configuration setting up domain name system servers that translate human readable domain names to IP addresses
- Proxy settings configuring intermediary servers for network traffic that can provide additional functionality like caching or filtering

#### System architecture overview

hardware at the bottom
kernel at the middle
application at the top 

kernel vs user space modern operation system divide memory and execution in to two distinict domain kerenel space and user space
kernel space runs privileged code with direct hardware access and contains critical os components 
user space runs application code with restricted privileges requiring kernel mediated access to hardware this separation enhances security and stability by preventing application from interfering with critical system operation 

### OS Components and Services

Operating systems provide essential services through specialized components:

- **Process vs. Thread**: A process is an independent program in execution with its own memory space, while a thread is a lightweight execution unit within a process that shares the process’s resources. Processes are isolated from each other, while threads within the same process can communicate more easily.
- **Scheduling Algorithms**: Operating systems use algorithms to determine which processes run and for how long. Common approaches include:
    - Round Robin: Each process gets a small time slice in circular order
    - Priority Scheduling: Higher priority processes run first
    - First-Come, First-Served: Processes run in the order they arrive
    - Shortest Job First: Processes with the shortest estimated run time execute first
    escalation (gaining higher privileges than intended),
### Windows Operating System
Windows Security Model
- **Windows Authentication:** Uses various authentication protocols including NTLM, Kerberos, and Windows Hello. Credentials are stored in the Security Account Manager (SAM) database or in Active Directory for domain environments.
- - **NTFS Permissions:** The New Technology File System (NTFS) provides robust security features including access control lists (ACLs) that specify which users or groups can perform operations on files and folders.
- - **Known Security Weaknesses:** Common vulnerabilities include legacy protocol support, excessive administrative privileges, outdated service defaults, and pass-the-hash attacks that exploit credential handling.

# Virtualization
### Hypervisor Types
Hypervisors come in two main categories, each with distinct characteristics:
- Type 1 (Bare Metal) Hypervisors run directly on the host’s hardware with no operating system beneath them. They have direct access to hardware resources, providing better performance, stronger security, and greater scalability. Examples include VMware ESXi, Microsoft Hyper-V Server, and KVM. These are primarily used in data centers and enterprise environments.
- Type 2 (Hosted) Hypervisors run on a conventional operating system like a regular application. They’re easier to set up but have additional overhead as they must go through the host OS to access hardware. Popular examples include Oracle VirtualBox (cross-platform), VMware Workstation Player (Windows/Linux), and VMware Fusion Player (Mac), making them ideal for desktop virtualization and testing.
## Containers and Docker
Lightweight Virtualization  
Containers provide a more efficient form of virtualization by sharing the host OS kernel while maintaining isolation between applications. This approach offers faster startup times, reduced resource usage, and improved deployment consistency.

**Virtualization** mimics the hardware, while **containers** mimic the operating system.
When you create a *VM* , you are installing a full copy of an operating system (like Windows or Linux) on top of virtual hardware.

*Containers* do not include an OS. They sit on top of the host’s operating system and share its "brain" (the kernel). They only contain the application and the specific libraries it needs to run.
### Docker Fundamentals
Docker uses a **client-server architecture**. When you run a Docker command, you aren't actually running the container yourself; you are sending a request to a background service that does the work for you.
docker engine
docker images
docker containers
docker registries
dockerfile
# The OSI Model
The OSI Model serves as a conceptual framework that standardizes the functions of telecommunication and computing systems. It divides network communication into seven logical layers, each handling specific aspects of data transmission. This layered approach helps in troubleshooting, development, and understanding the complex process of network communication.

The TCP/IP model, which emerged from ARPANET research, is the practical implementation that powers the internet today. It uses four layers (Network Interface, Internet, Transport, and Application) compared to the OSI Model’s seven layers. While OSI is primarily conceptual and educational, TCP/IP is the actual protocol suite used in real-world networking. The OSI Model provides a more detailed view of networking functions, while TCP/IP offers a more practical implementation-focused approach.

### Layer 7: Application Layer

Key Protocols and Services

- **HTTP/HTTPS**: Hypertext Transfer Protocol for web browsing; HTTPS adds SSL/TLS encryption for secure communication
- **SMTP/POP3/IMAP**: Email protocols for sending (SMTP) and receiving (POP3, IMAP) messages
- **FTP/SFTP**: File Transfer Protocol and its secure variant for transferring files between systems
- **DNS**: Domain Name System for resolving domain names to IP addresses
- **DHCP**: Dynamic Host Configuration Protocol for automatic IP address assignment
- **Telnet/SSH**: Protocols for remote terminal access; SSH provides encrypted connections
- **SNMP**: Simple Network Management Protocol for managing network devices

### Layer 6: Presentation Layer

- **Data Encryption/Decryption**: SSL/TLS protocols provide security by encrypting data
- - **Data Compression**: Reduces bandwidth requirements by compressing data before transmission
- - **Character Encoding**: ASCII, Unicode (UTF-8, UTF-16), EBCDIC conversion
- - **Data Formatting**: Converting between different data formats like XML, JSON, or binary formats
- **Media Formatting**: JPEG, GIF, MPEG, MIDI formatting for images, video, and audio
 ### Layer 5: Session Layer
 
 Key Functions and Protocols
 
- **NetBIOS**: Network Basic Input/Output System for session services on Windows networks
- **RPC**: Remote Procedure Call for client-server communication
- **SIP**: Session Initiation Protocol for voice and video call setup
- **H.323**: Protocol suite for audio-visual communication sessions
- **SQL**: While primarily an Application layer protocol, SQL maintains database sessions
- **NFS**: Network File System includes session functionality for file access
### Layer 4: Transport Layer
- **TCP (Transmission Control Protocol)**: Connection-oriented protocol providing reliable, ordered, and error-checked delivery. TCP establishes a connection before data transfer (three-way handshake), implements flow control, congestion control, and ensures data integrity through checksums and acknowledgments.
- - **UDP (User Datagram Protocol)**: Connectionless protocol offering a simple, unreliable datagram service. UDP provides faster transmission with minimal overhead but without guarantees for delivery, ordering, or duplicate protection. It’s suitable for applications that prioritize speed over reliability.
- - **SCTP (Stream Control Transmission Protocol)**: Combines features of both TCP and UDP, providing message-oriented reliable transport with multi-streaming and multi-homing capabilities.
- - **DCCP (Datagram Congestion Control Protocol)**: Provides congestion control for applications that prefer timeliness over reliability.
### Layer 3: Network Layer

- **IP (Internet Protocol)**: The primary protocol that routes packets across networks using IP addresses for logical addressing. IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses to overcome IPv4 address exhaustion.
-  **ICMP (Internet Control Message Protocol)**: Used for diagnostic and error reporting functions. ICMP handles error messages and operational information, such as “destination unreachable” or “time exceeded” messages.
- - **Routing Protocols**:
    - **OSPF (Open Shortest Path First)**: Link-state routing protocol for interior gateway routing
    - **BGP (Border Gateway Protocol)**: Path-vector routing protocol for exterior gateway routing between autonomous systems
    - **RIP (Routing Information Protocol)**: Distance-vector routing protocol for interior gateway routing
    - **EIGRP (Enhanced Interior Gateway Routing Protocol)**: Advanced distance-vector routing protocol
- **IPsec**: Security protocol suite for securing IP communications through authentication and encryption

### Layer 2: Data Link Layer

- **Ethernet**: The most common LAN technology, defining frame formats, addressing, and CSMA/CD access method
- **Wi-Fi (802.11)**: Wireless networking standard with various versions (a/b/g/n/ac/ax)
- **ARP (Address Resolution Protocol)**: Maps IP addresses to MAC addresses
- **PPP (Point-to-Point Protocol)**: Used for direct connections between two nodes
- **HDLC (High-Level Data Link Control)**: Bit-oriented synchronous data link layer protocol
- **Switches**: Network devices operating at this layer that forward frames based on MAC addresses
- **Bridges**: Connect separate network segments and operate at the Data Link layer

### Layer 1: Physical Layer

- **Physical Media**:
    - **Copper Cable**: Twisted pair (UTP/STP), coaxial
    - **Fiber Optic Cable**: Single-mode, multi-mode
    - **Wireless**: Radio frequencies, microwave, infrared  
- **Network Components**:
    - **Hubs**: Multi-port repeaters operating at the Physical layer
    - **Repeaters**: Amplify or regenerate signals to extend transmission distances
    - **Network Interface Cards (NICs)**: Hardware interfaces connecting devices to networks
    - **Transceivers**: Transmit and receive data over the physical medium
- **Standards and Interfaces**:
    - **Ethernet Physical Layer**: 10BASE-T, 100BASE-TX, 1000BASE-T, 10GBASE-T
    - **USB**: Universal Serial Bus specifications
    - **RS-232/RS-485**: Serial communication standards
    - **DSL/ISDN**: Digital subscriber line technologies

## TCP/IP Model

The TCP/IP (Transmission Control Protocol/Internet Protocol) model is a simplified version of the OSI model, widely used in modern networking.

*Application Layer* Combines the functions of the OSI model’s Application, Presentation, and Session layers. Protocols like HTTP, FTP, SMTP, and Telnet operate at this layer.

*Transport Layer* Provides end-to-end communication and ensures reliable data delivery. The two main protocols in this layer are TCP (connection-oriented) and UDP (connectionless).

*Internet Layer* Responsible for addressing, packaging, and routing data across the network. The primary protocol at this layer is IP (Internet Protocol), which comes in two versions: IPv4 and IPv6.

*Network Access Layer* Combines the functions of the OSI model’s Physical and Data Link layers, dealing with the physical transmission of data and hardware addressing (MAC addresses).


##### Routing Tables
**Components of a Routing Table:**

- **Destination Network/Host**: The target network or host address
- **Network Mask**: Defines the network portion of the destination address
- **Gateway/Next Hop**: Address of the next router to forward packets toward the destination
- **Interface**: Network interface to use for forwarding packets
- **Metric**: Value indicating route preference (lower is better)
- **Flags**: Indicators of route status and type (Up, Gateway, Host, etc.)


**Viewing Routing Tables:**
#### Linux/macOS
route -n          # Classic command showing numerical addresses
ip route show     # Modern command with more detailed output

#### Windows
route print       # Detailed routing table view
netstat -r        # Alternative command showing routing information

**Adding and Removing Routes:**
#### Linux
`ip route add 192.168.2.0/24 via 192.168.1.1    # Add a route`
`ip route del 192.168.2.0/24                   # Remove a route`

#### Windows
`route add 192.168.2.0 mask 255.255.255.0 192.168.1.1`
`route delete 192.168.2.0


### IPv6 Address Types

**Unicast Addresses** - Identify a single interface:

- **Global Unicast Addresses (GUA)**: Publicly routable addresses similar to IPv4 public addresses, generally starting with 2000::/3
- **Link-Local Addresses**: Automatically configured on every IPv6 interface, used for communication on the local network segment only, always begin with`fe80::/10`
- **Unique Local Addresses (ULA)**: Private addresses for local communications not intended to be routed on the internet, similar to IPv4 private addresses, begin with `fc00::/7` (typically fd00::/8 in practice)
- **Loopback Address**: ::1/128 (equivalent to 127.0.0.1 in IPv4)
- **Unspecified Address**: ::/128 (similar to 0.0.0.0 in IPv4)

**Multicast Addresses** - Identify multiple interfaces, packets sent to a multicast address are delivered to all interfaces identified by that address:

- Always begin with ff00::/8


**Anycast Addresses** - Assigned to multiple interfaces, but packets are delivered only to the nearest one based on routing metrics:

- Syntactically indistinguishable from unicast addresses
- Used for service discovery and load balancing
- Example applications include DNS root servers and content delivery networks

IPv6 eliminated the concept of broadcast addresses, replacing their functionality with specific multicast groups for more efficient network usage.

#### IPv4 to IPv6 Transition Mechanisms

**Dual Stack** - Running both IPv4 and IPv6 simultaneously:
**Tunneling** - Encapsulating IPv6 packets within IPv4 packets to traverse IPv4-only networks:

- **6in4/Manual Tunnels**: Explicitly configured tunnels between endpoints
- **6to4**: Automatic tunneling using 2002::/16 address space based on IPv4 addresses
- **6rd (Rapid Deployment)**: Provider-specific implementation similar to 6to4 but within an ISP’s network
- **Teredo**: Encapsulates IPv6 in UDP/IPv4 packets to traverse NATs
- **ISATAP**: Intra-Site Automatic Tunnel Addressing Protocol for internal networks

**Standard Allocation Model**:

- The Internet Assigned Numbers Authority (IANA) allocates /12 blocks to Regional Internet Registries (RIRs)
- RIRs typically allocate /32 blocks to ISPs
- ISPs often allocate /48 blocks to organizations
- Organizations subdivide their /48 into /64 subnets
- Each /64 subnet provides 2^64 (18.4 quintillion) addresses for a single network segment


# Authentication and Authorization
Authentication verifies `who you are`
authorization determines `what you’re allowed to do.`

### Access Control Implementation
A fundamental security concept in authorization is the **Principle of Least Privilege (PoLP),** which states that users should be given the minimum levels of access necessary to complete their job functions. This principle limits the potential damage from accidents, errors, or malicious actions and reduces the attack surface of systems.

## Encryption Fundamentals

Symmetric Encryption 
Symmetric encryption uses the same key for both encryption and decryption:

How It Works:

1. A single secret key is established between communicating parties
2. The sender encrypts data using this key
3. The receiver decrypts data using the same key

Common Algorithms:

- **AES (Advanced Encryption Standard):** Modern, highly secure block cipher with key sizes of 128, 192, or 256 bits
- **3DES (Triple DES):** Applies DES encryption algorithm three times to each data block
- **ChaCha20:** Stream cipher designed for high-speed software implementations

Asymmetric Encryption

Asymmetric encryption (also called public-key cryptography) uses different but mathematically related keys for encryption and decryption:

How It Works:

1. Each participant generates a key pair: a public key and a private key
2. Public keys are openly shared, while private keys are kept secret
3. Data encrypted with a public key can only be decrypted with the corresponding private key
4. Data encrypted with a private key can be verified with the corresponding public key (used for digital signatures)

Common Algorithms:

- **RSA:** Based on the factoring problem of large composite numbers
- **ECC (Elliptic Curve Cryptography):** Based on algebraic structures of elliptic curves
- **Diffie-Hellman:** Used primarily for key exchange rather than encryption
-
## Hashing in Detail

**Properties of Cryptographic Hash Functions**

**Common Hashing Algorithms**

Practical Applications of Hashing

## Common Encoding Methods

Encoding is Not Encryption  
Remember that encoding transforms data format for compatibility or transmission purposes without any security intent. Since encoding schemes are standardized and public, they provide no confidentiality. Never use encoding alone to protect sensitive information - that’s what encryption is for.

Base64 Encoding

Base64 encoding converts binary data to an ASCII string format using 64 printable characters (A-Z, a-z, 0-9, +, /). It’s commonly used to:

- Embed binary data in text-based formats (like email attachments in MIME)
- Include binary data in XML, JSON, or HTML documents
- Transmit binary data through text-based protocols
- Represent binary data in URLs (with slight modifications)

Example: “Hello” in Base64 is “SGVsbG8=”

URL Encoding

URL encoding (also called percent-encoding) converts characters into a format that can be transmitted over the Internet. It replaces unsafe ASCII characters with a “%” followed by two hexadecimal digits. Used for:

- Making URLs safe by encoding special characters
- Encoding form data submitted via HTTP
- Ensuring consistent interpretation of URLs across systems

Example: “Hello World!” in URL encoding is “Hello%20World%21”

  

Hexadecimal Encoding

Hexadecimal (base-16) encoding represents binary data using 16 different symbols (0-9 and A-F). Each byte is represented as two hex digits. It’s commonly used for:

- Representing binary data in a human-readable format
- Representing color values in web design (e.g., #FF5733)
- Displaying cryptographic hashes and checksums
- Viewing raw memory contents and binary files

Example: “Hello” in hex is “48 65 6C 6C 6F”

Unicode Encoding

Unicode is a standard for encoding, representing, and handling text from all the world’s writing systems. Common Unicode encodings include:

- **UTF-8:** Variable-width encoding that uses 1-4 bytes per character; dominant encoding for the web
- **UTF-16:** Uses either 2 or 4 bytes per character; used in Windows APIs
- **UTF-32:** Fixed-width encoding using 4 bytes per character; simplest to process

These encodings allow computers to store and exchange text in any language and script.

## Real-World Applications

Securing Communications: HTTPS

Password Storage Best Practices

**Digital Signatures and Certificates**

## Practical Exercise

Now it’s time to put your knowledge into practice! We’ll use CyberChef, a powerful web-based tool for data analysis and cryptographic operations. CyberChef is often called the “Cyber Swiss Army Knife” because of its versatility in handling various encoding, encryption, and hashing tasks.

Using CyberChef  
CyberChef is a free, browser-based tool developed by GCHQ that allows you to perform cryptographic operations without installing any software. Visit [https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/) to access the tool. Simply drag operations from the left panel into the recipe area, input your data, and see the results instantly!

**Practical 1:** Base64 Encoding Challenge

**Practical 2:** Hashing Challenge

**Practical 3:** Encryption Challenge

**Bonus Challenge:** Combining All Three Techniques

Reflect:  
After completing these exercises, think about the data you’ve transmitted online today. Which of these cryptographic techniques were likely protecting your information? Consider your online banking, email, social media, or shopping activities. What might happen if these cryptographic protections were removed?

[

](https://savanna.alxafrica.com/concepts/113503?project_id=103053)

Copyright © 2026 ALX, All rights reserved.