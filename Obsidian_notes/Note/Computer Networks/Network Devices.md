Network Devices are physical devices that allow computer and other devices to communicate and exchange data within a network

network devices are divided into mainly 2 types intra-network and inter-network

1. Repeater
	* A Repeater is a device that regenerates and amplifies signals to extend the transmission distance
	* When signals Travels through cables they become weak repeater solves this
	* 2 port device works at physical layer
* Types of Repeaters
	* Analog 
	* digital
	* wired
	* wireless
	* local
	* remote
2. HUB
	+ A hub is a multi-port Repeater
	+ It connects multiple computers in a star topology
	+ Hub receives a data packet
		+ send the packet to all connected devices
	+ works on physical layer
	+ no filtering no intelligence 
3. Bridge
	+ A bridge connects Two LAN's using the same protocol
	+ It works on Data link layer
	+ Bridge works by reading the MAC address then decides to either forward frame or block frame
+ bridge filters network traffic only pessary data passes 
+ Two port device
+ connects Two networks
+ uses MAC address filtering
	1. Types of Bridges
		+ Transparent bridge: stations unaware of bridge
		+ automatically learns addresses
		+ uses two processes:learning and forwarding
	2. Source Routing bridge
		+ The source device decides the route
		+ special frame used: discovery frame
		+ it travels across the network to discover paths 
4.  Switch
	+ A switch is a multi-port bridge that improves network performance
	+ IT works at Data link layer
	+ Switch works by storing MAC address table
		+ When frame arrives Read MAC address
		+ identify correct port
		+ send frame only to that port
		+ faster than hub reduce traffic efficient communication performs error checking

5.  Router
	+ A router connects different networks and routers packets using ip address
	+ router operates at network layer
		+ Router connects LAN and WAN choose the best path and maintain routing table
6. Gate way
	+ A Gateway connects networks that use different protocols 
	+ gateway Translate between them It acts as an Protocol converter
	+ Work on any OSI layer More complex than router and switches
7. NIC {Network Interface Card}
	- NIC is a hardware component that connects a computer to a network
	- Every computer in LAN must have a NIC
	- A NIC should contain Network chip connector and MAC address

**MAC address**
NIC contains a unique identifier this address identifies device in a network

### Protocols
- Protocols are rules that control communication between devices
	- TCP
	- IP
	- HTTP
	- SMTP
	- UDP

**Elements of protocol**
- Syntax-**Structure and format of data**
- semantics-**Meaning of data and Actions taken**
- Timing -**Timing control transmission speed **

**Sequence Control**
- Sequence Control ensures:
	- data packets arrive in correct order
	- Lost packets are re-transmitted
**Flow Control**
Flow Control regulates:
- Sender speed vs receiver speed
**Error Control**
- Error control detects and fixes error during transmission
- CRC
- Parity
- Re-transmission
**Network security**
- Protocols also ensure:
- Data confidentiality
- authentication
- Data integrity
Security methods include
- Encryption
- access control
- authentication

**Standards**
- Standards are rules that defines how devices communicate in networks
- they ensure compatibility between devices
- IEEE,ISO,ANSI

## Types of Standards
 De Facto Standard

Meaning:

**“By fact”**

Not officially approved but widely used.

De Jure Standard

Meaning:

**“By law”**

Officially approved by standards organizations.

Examples:

- TCP
    
- IP
    
- SMTP
    
- UDP

# Importance of Protocol & Standards

They provide:

### 1️⃣ Interoperability

Devices from different companies can communicate.

Example:

Laptop ↔ Router ↔ Server

---

### 2️⃣ Security Baseline

Protocols provide security rules like:

✔ Encryption  
✔ Authentication

---

### 3️⃣ Vulnerability Management

Standards help organizations:

✔ Identify security risks  
✔ Fix vulnerabilities



| Device   | OSI Layer | Function                  |
| -------- | --------- | ------------------------- |
| Repeater | Physical  | Regenerate signal         |
| Hub      | Physical  | Broadcast data            |
| Bridge   | Data Link | Filter frames             |
| Switch   | Data Link | Forward frames using MAC  |
| Router   | Network   | Route packets using IP    |
| Gateway  | Any layer | Protocol conversion       |
| NIC      | Hardware  | Connect device to network |