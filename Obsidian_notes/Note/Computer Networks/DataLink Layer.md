Data link layer is the 2nd layer of the OSI model

## OSI Layers

+ Physical Layer
+ Data Link Layer
+ Network Layer
+ Transport Layer
+ Session Layer
+ Presentation Layer
+ Application Layer

Main responsibility of the data link layer is to ensure that there is 
+ Reliable Data transfer
+ Error Detection
+ Flow Control
+ Frame organization

It sits between the Physical layer and network layer

## Function of data link layer

1. Provides Services interface to network layer
	 + The DDL provides services to the Network Layer above it
		 + Network layer -> sends packets
		 + data link layer -> Converts packets into frames
	+ So that the network layer does not have to worry about physical transmission
2. Framing
	+ Data must be transmitted in structured units These units are called **Frames**
	+ Frames are streams of bits divided into manageable blocks
	+ Each frame contains 
		+ Header - Control information
		+ Data  - Actual message
		+ Trailer - Error checking
3. Error Control 
	+ Errors occur due to:
		+ Noise
		+ Signal interference
		+ Hardware Faults
	+ The error is detected or corrected by using:
		+ Parity
		+ Checksum
		+ CRC
		+ Hamming code
4. Flow Control
	+ Ensures Fast sends does not overwhelm a slow receiver
	+ Without Flow control → buffer overflow


## Services provided to network layer

It provides 3 types of services

1. Unacknowledged connection service
	+ No Connection established
	+ Frames send independently
+ if frame lost->ignored
+ Used in voice communication
2. Acknowledged communication
	+ No connection setup
	+ each fame is acknowledged
	+ Sender -> sends frame
		+ Receiver -> sends ACK
			+ If ACK not received -> resend
3. Acknowledged connection - oriented service
	`Most reliable`
	+ Connection established
	+ Data transmitted
	+ Frames acknowledged
	+ connection released
	make sure every fame is received no duplication correct order

## Framing
framing defines how frames start and end

1. Fame count method
	+ `Length | Data`
		+ `7 | ABCDEFG` reads 7 bytes
	+ Problems
		+ If the length filed is corrupted receiver looses frame boundary There fore not commonly used today
2. Byte Stuffing
	+ Frame Boundaries marked by flag bytes
		+ `FLAG | DATA | FLAG`
	+ Problems
		+ If FLAG appears inside data
		+ solution
			+ Insert ESC character before flag
				+ Original data `DATA FLAG DATA` Transmitted data `DATA ESC FLAG DATA`
3. Bit stuffing
	+ Used in bit oriented protocols
	+ frame begins with special flag:
		+ `0111110`
		+ Rule: If sender sees 5 1s it insert a 0bit automatically
		+ Original:`01111110`  After stuffing:`011111010`  Receiver removes the extra 0.
4. Physical Layer Coding Violations
	+ Uses invalid physical signals to make frame boundaries

## Error Control
error occurs due to:
+ electrical interference
+ signal attenuation
+ Noise
The solution can be Detection and correction 
# Single Bit Error

Only **one bit changes**.

Example:

Original: 100101  
Received: 100111

Only one bit flipped.

Rare in serial communication.

---

# Multiple Bit Error

More than one **non-consecutive bit** changes.

Example:

Original: 10100101  
Received: 10110111

---

# Burst Error

Multiple bits corrupted together.

Example:

Original: 1011100010  
Received: 1000010010
Common in **serial transmission**.

----





