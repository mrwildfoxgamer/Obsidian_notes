
A computer network is a system where multiple computers are connected so they can communicate and share resources

`Arpanet - Advanced research project agency network created by US depratment of defance and arpa research agency`

`Nefnet - national science foundation network first backbone of the mordean internet`

`internet - it is a globally connectd system that uses TCP/IP protocols to transmit data between devices`

## Client server model
This is one of the most important networking concepts

`Server is a powerfull computer that provides services`
`Client is a device that requests services from the server`

## Types of computer networks

Networks are classified by size and coverage area

1. Personal area network (pan)
	1. 1 to 100 meters
	2. Used for devices  around a person
	3. `blootooth` `wireless keyboards` `Usb calbes`
2. Local area networks (LAN)
	1. Range up to 2km 
	2. LAN covers `home` `offices` `schools`
	3. `Ethernet` `wifi` 
3. Metropolitan Area network (MAN)
	1. Man covers citys
	2. `cable tv` `Bank networks in one city` 
	3. 5 to 50 km
	4. `Fiber optic cables`
	5. Wide Area Networks(WAN)
		1. Wan covers very large geographical areas
		2. `internet`
		3. more than 50km


## Network Topology
Topology means how computers are physically or logically arranged in a network

+ Point to point
+ Bus
+ Ring
+ Star
+ Mesh
+ Tree
+ Hybrid

1. Point to point Topology
	1. Simplest topology
	2. Two computers connected directly
	3. `computer <-> keyboard`
	4. High bandwidth simple communication
2. Bus Topology
	1. All devices connected to one main cable
	2. Message travels to all devices
	3. if the backbone (bus) Fails entire network fails
	4. CSMA(Carrier Sense Multiple Access) Used to control the traffic
		+ CSMA/CD Collision Detection
			+ If two devices send data simultaneously Collision detected transmission stops
		+ CSMA/CA Collision Avoidance
			+ Before sending data checks if channel is free
				+ used in Wi-Fi networks
3. Ring Topology
	1. Computer forms a circle network
	2. data flows in one direction
	3. A special signal called token circulates only device with the token can send data
	4. Few collisions, High speed
	5. If one node fails all network fails
4. Star Topology
	1. Most common topology
	2. all computers are connected to a central hub or switch
	3. If the central hub fails the whole network fails
	4. Easy to trouble shoot , easy expansion , High speed
5. Tree topology
	1. Combination of `star` `bus` topology structure looks like tree hierarchy
	2. easly expandable, easy management
	3. expensive, Main cable failure affects network
6. Mesh topology
	1. Every computer connects to every other computer
	2. `internet strcutre`
		+ Full mesh - every computer is conneted to evey other computer
		+ partial mesh - Only important devices connected
	3. very relable, high security
	4. expensive , complex installation
7. Hybrid Topology
	1. Combination of multiple topologys
	2. flexible , scalable
	3. very expensive , complex design