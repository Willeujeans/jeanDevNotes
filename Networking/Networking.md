# Networking

# Packets
*A small unit of data that travels across a network*
## Header
- Contains source address
- Destination addresses
- Sequence numbers
- Protocol information
## Payload
- Contains actual data to be transferred 

Packets are transmitted from one network device to another using networking protocols such as [[Transmission-Control-Protocol]]. They travel across routers, switches, and other network devices, following predefined routes to reach their destination. 

---
# Protocols
## Sliding Window Protocol
*networking model in packet based transmissions*

[[Transmission-Control-Protocol]] uses sliding windows protocols

The "sliding window" is a group of data that gets sent, this data transfer can have multiple different approaches.
The sender maintains a window of packets it can transmit without acknowledgment.
### Example
```
N = no data
B = buffered data
A = acknowledgment 
T = transmission confirmed
D = data was delivered

-------------------< Sliding window is established with n size
 {B  B  B} B  B  B  
  |  |  |  |  |  | 
  |  |  |  |  |  | 
  N  N  N  N  N  N 
-------------------< Buffered data is sent at the start of the window
 {B  B  B} B  B  B 
  B  |  |  |  |  |  
  N  N  N  N  N  N 
-------------------< Data was delivered, an ACK is being sent back
 {B  B  B} B  B  B 
  A  |  |  |  |  | 
  D  N  N  N  N  N 
-------------------< ACK delivered, transmission confirmed, window moves
  T {B  B  B} B  B 
  |  |  |  |  |  | 
  |  |  |  |  |  | 
  D  N  N  N  N  N 
```
### Go back N
- Sender can send up N packets in window without needing acknowledgment
- If an acknowledgment is not received within a certain timeout period
	- Sender assumes that one or more packets have been lost
	- Then sender retransmits all unacknowledged packets starting from the earliest unacknowledged packet.
### Selective Repeat
Upon receiving a packet, the receiver checks if it is in sequence
If the packet is in sequence, it is accepted, and an acknowledgment (ACK) is sent back to the sender
If the packet is out of sequence it is buffered but not acknowledged
Receiver sends acknowledgments for correctly received packets
Indicating the highest sequence number it has received successfully
Sender maintains a timer for each packet sent, sender does not receive an acknowledgment for a specific packet within a certain timeout period it retransmits

---
## Transmission Control Protocol
*allows devices and programs to exchange messages over a network*

Uses Internet-Protocol
Sends Packets across networks to deliver data.

The server is outputting a passive signal
The client makes an active connection
### Commands
	URG
	ACK
	PSH
	RST
	SYN
	FIN

---------------------------------------------------< CLIENT TO SERVER OUTREACH
01. CLIENT---| SYN               Seq 00 |-->SERVER 
02. CLIENT<--| ACK SYN   Ack 01  Seq 00 |---SERVER
03. CLIENT---| ACK       Ack 01  Seq 01 |-->SERVER
----------------------------------------------------< HANDSHAKE ESTABLISHED
04. CLIENT<--| 22 BYTES          Seq 01 |---SERVER
05. CLIENT---| ACK       Ack 23         |-->SERVER
----------------------------------------------------< TERMINATION DECICION
06. CLIENT<--| FIN               Seq 23 |---SERVER
07. CLIENT---| ACK               Ack 24 |-->SERVER
08. CLIENT---| FIN               Seq 01 |-->SERVER
09. CLIENT<--| ACK               Seq 02 |---SERVER
----------------------------------------------------< END OF HANDSHAKE

01. CLIENT sends synchronize(SYN) with sequence number 0
02. SERVER sends acknowledgement with acknowledgment number 1, it now expects 1 to be sent as the sequence number from CLIENT, SERVER sends synchronize with sequence number of 0
03. CLIENT sends an acknowledgement with number of 1
   CLIENT sends sequence 1
04. SERVER sends complex data to CLIENT in form of 22 BYTES with Seq 1
05. CLIENT Acknowledges this with the next step Ack 22 + 1 = 23
06. SERVER sends FIN statement with Seq 23
07. CLIENT acknowledge with Seq 23 + 1 = 24
08. FIN with Seq 01
09. SERVER acknowledges with Seq 1 + 1 = 2 

#### Application layer - HTTP, SMTP
port, uses a port for the transport
#### Transport layer - TCP, UDP
breaks data into Packets
The protocol sends data about the order
So if theres any mistakes it will resend that packet
#### Internet Layer
Attaches the origin and destination IP addresses

*Higher level protocols that use TCP*
- *File Transfer Protocol*
- *Secure Shell*
- *Internet Message Access Protocol*
- *Post Office Protocol*
- *Simple Mail Transfer Protocol*
- *Hypertext Transfer Protocol*
### History
- Designed in the 1970s by DARPA scientists Vint Cerf and Bob Kahn
- TCP is one of the basic standards that define the rules of the internet and is included within the standards defined by the Internet Engineering Task Force (IETF)

---
## Internet Protocol
*Provides addressing and routing mechanisms for packets to transfer over networks*
Helps with moving data to where it needs to go across multiple networks.
IP addresses serve unique identifiers for devices on networks
It's akin to a postal address for the internet.

---
# Server
_A specialized computer system that provides services to other computers_
A server can be a dedicated hardware device or a software program running on a computer system this would be an example of a [[Virtual-Machine]] used as a server.
## Network Accessibility:
Servers are accessible over a network, such as the internet or a [[Local Area Network]].
Clients connect to servers using protocols such as
- [[Hypertext Transfer Protocol]]
- [[File Transfer Protocol]]
- [[Simple Mail Transfer Protocol]]
depending on the type of service being provided.

---
# Socket Programming
*client and server communication*
## Server socket
Special socket that a server uses to listen for connection requests from clients
## Socket
objects used to send data
## IP Address
Apartment building
## Port number
the apartment in that building
## DataInputStream
Read
## DataOutputStream
Write