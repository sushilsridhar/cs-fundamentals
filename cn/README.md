# Computer Networks

computers need to talk to eachother to exchange data    

<ins>Protocol</ins> is a set of rules that governs the transmission between two computers       

# OSI model
Open Systems Interconnection
> OSI model is a reference model/tool to actually model or trace the actual flow of how data transfers in networks 

> It is a logical representation of how the network systems are supposed to send data (or, communicate) to each other  

![Screenshot 2022-12-29 at 9 36 12 AM](https://user-images.githubusercontent.com/16437905/209902138-a158630d-d749-40fa-ac7b-6895f509ed1f.png)

# Internet Protocol Suite - TCP/IP 
> OSI model is a reference model while TCP/IP is an implementation of OSI model

TCP/IP Model helps you to determine how a specific computer should be connected to the internet and how data should be transmitted between them 

OSI model gives guidelines on how communication needs to be done, while TCP/IP protocols layout standards on which the Internet was developed

> TCP/IP specifies how data should be packetized, addressed, transmitted, routed, and received on a network by providing end-to-end communication

> there are 4 layer in TCP/IP model       

> Each layer is responsible for a particular task strictly according to the protocols   

![The-logical-mapping-between-OSI-basic-reference-model-and-the-TCP-IP-stack](https://user-images.githubusercontent.com/16437905/202834288-127fcd13-48ef-433c-b7dd-5d846f79f831.jpg)

![Screenshot 2022-12-29 at 12 39 42 PM](https://user-images.githubusercontent.com/16437905/209916392-f23ef347-e173-4b8f-b455-3e5dcfd54aeb.png)

# Application Layer   

``` 
Job       : Generate the data on the sender side to be sent / recieve the data on reciever side
Protocols : HTTP
```
[HTTP is Client-Server architecture protocol](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/APP_LAYER_ARCHITECTURE.md)

[HTTP is Stateless protocol](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/HTTP.md)

# Transport Layer     

```
Protocol  : Transmission Control Protocol (TCP)
Job       : determine how to send the data packets from source to destination
```

Transmission Control Protocol (TCP) The transmission control protocol (TCP) is a transport layer protocol that works along with the internet protocol to transmit data over the internet. It is a connection-oriented and reliable protocol i.e. it establishes the connection first and then only, sends data over the established connection hence, there is no packet loss in the transmission control protocol.

Transmission Control Protocol is responsible for the delivery of data once the Internet protocol gets the IP address of the destination.

# Internet Layer     

```
Protocol  : Internet Protocol (IP)
Job       : determine how to send the data packets from source to destination, divides data recieved into packets
```

Internet Protocol (IP) The internet protocol is a network layer protocol that is responsible for defining the rules that define how the information is sent over an internet connection from one computer to another    

Internet Protocol is responsible for gathering the addresses to which the data is to be transmitted.

he network layer divides the data received from the transport layer in the form of packets.
The network layer provides two ways of communication namely - connection-oriented and connectionless.


# Network Interface Layer        

Data link layer
```
Job of layer   : convert data into frames (bits of stream with header and trailer)
Protocol used  : Ethernet IEEE 802.2 framing and Point-to-Point Protocol (PPP) framing.
```
> Framing is the technique in which the data is divided into streams of bits (called frames)    

the data link layer adds a header and trailer to the frames, The header (present at the starting of the frame) contains the hardware's physical address of source and destination. The trailer (present at the end of the frame) contains the error detection and correction bits

link MAC here

These bits are used to detect the errors and then retransmit the damaged or lost data to prevent any kind of duplication.

<ins>Work</ins>   
flow control - maintains the rate of data transmission and data absorption

the data link layer adds the error detection and correction bits at the end of the frames in the form of trailers. These bits are used to detect the errors and then retransmit the damaged or lost data to prevent any kind of duplication.

<ins>Physical layer</ins>       
```
Job of layer   : transmission and reception of the signals over the physical medium, 

                 transmission - (convert bitstream of data to signals)
                 reception    - (convert signals to bitstream of data)
                 
Protocol used  : Ethernet
```

> The bits of data must be encoded into the form of signals for transmission    

The physical layer receives the frames from the Data Link Layer and generates information on bits of electrical impulses or light depending on the medium being optical or electrical and transmits them physically bit by bit    

<ins>Work</ins>   
the physical layer sets the voltages, light speed(in the case of fiber optics cable), and data rates (numbers of bits to be transmitted per second)     

deals with network topology (A logical topology is how devices appear connected to the user. A physical topology is how they are actually interconnected with wires and cables)           
deals with direction and type of transmission (simplex, half-duplex, full-duplex)   

<ins>Ethernet</ins>   
Ethernet uses the logical bus topology to transfer data. Under a bus topology a node broadcasts the data to the entire network. All other nodes on the network hear the data and check if the data is intended for them

# End to End flow

DNS   
Sending request to the server to access the webpage and receiving response Once we get the IP address of the website we want to access using DNS, the browser sends an HTTP (Hypertext Transfer Protocol) request to the server to extract the HTM (Hypertext Markup Language)L webpage corresponding to the IP address. This request is sent over PORT 80 using TCP (Transmission Control Protocol). Once the server receives this HTTP request, it responds back with an HTTP response. This HTTP response consists of the information related to the HTML page corresponding to the IP address of the website.
