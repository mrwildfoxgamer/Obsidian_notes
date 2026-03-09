It is the technique used to manage the rate of data transmission between sender and receiver

`ensuring the sender does not send data faster than the recever can process it`

Flow control is one of the most important functions of the data link layer it ensures
- Proper communication
- no data loss
- Efficient transmission

## Buffer concept

Receiver has limited memory (buffer) The buffer temporarily stores incoming frames until processed. If buffer is full the  receiver tells the sender  to stop sending temporarily


## Stop-and-Wait Protocol
This is the simplest flow control method 
- Sender sends one frame
- sender waits for ACK(acknowledgement)
- After ACK -> send next frame
### Problems
+ Lost Frame
	+ Receiver never gets it
	+ time expires
	+ sender re-transmits frame
+ Lost ACK
	+ Receiver receives frame, but ACK lost
	+ Sender things frame lost → sends again
	+ Receiver discards duplicate frame
# Timer Mechanism
Sender starts a timer after sending frame

if ACK not received before timer expires
- Sender assumes frame lost
- Frame is re-transmitted

## Piggybacking
- piggybacking improves efficiency 
- Instead of sending separate ACK:
- ACK is attached with outgoing data frame
-  This reduces Traffic and saves bandwidth

## Disadvantages of stop and wait
- Only one frame is transmitted at a time
- Network bandwidth is wasted sending ACK after each frame 
	- Solution: send multiple frames before ACK
		- Protocols for solving this: Go-back-N, Selective repeat
## Sliding Window Protocol

Sliding window allows sender to send multiple frames before receiving ACKs

window=range of frames that can be sent

```
window size=4

sender sends:Frame0 Frame1 Frame2 Frame3 Frame4
before wating for ACK
```

Sender keeps frames in windows until acknowledged
```
Window =[0 1 2 3 ]
if ACK0 received

Window slides forward:
Window=[1 2 3 4]
```

### Receiver Sliding Window
in GO-BACK-N

receiver window size=1
Receiver accepts only expected frame
if unexpected frame arrives discards


## Control variables

Sender maintains 3 variables
S-last frame
SF-First frame
SL-Last frame in window

Receiver variables
R - Expected frame

## Go-BACK-N ARQ
improved Protocol

Sender can send multiple frames without waiting
but if error occurs:
Sender re transmits from error frame onward

```
Sender sends:

0 1 2 3

Frame 2 lost

Receiver receives frame 3.

But expects frame 2.

Receiver discards frame 3.

Sender timeout occurs.

Sender retransmits:

2 3

Hence name:

Go Back N
```

Cumulative ACK

Receiver may Acknowledge multiple frames

eg: ACK4 means frames 0,1,2,3 received successfully

## Lost ACK in go-BACK-N
if ACK lost but later ACK arrives:

examples:
ACK1 LOST
ACK2 LOST
ACK3 LOST

but ACK4 arrives

sender understands frames 0-3 received
no re-transmission needed 

### Selective Repeat ARQ
This protocol improves efficiency

Defference:

+ Go-Back_N ->re-transmit many frames
+ Selective Repeat -> re-transmit only lost frame
+ ```
  Sender sends:

0 1 2 3

Frame 2 lost.

Receiver receives frame 3.

Instead of discarding:

Receiver stores frame 3.

Receiver sends:

NAK2

Sender retransmits only:

Frame2
  ```
+ Higher efficiency
+ Less re-transmission
+ better bandwidth usage
+ More complex
+ Receiver must buffer frames

|Protocol|Frames sent|Retransmission|
|---|---|---|
|Stop & Wait|1|resend same frame|
|Go Back N|many|resend from error|
|Selective Repeat|many|resend only error frame|

