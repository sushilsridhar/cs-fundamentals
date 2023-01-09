# Computer Networks

computers need to talk to eachother to exchange data    

<ins>Protocol</ins> is a set of rules that governs the transmission between two computers       

<ins>Internet</ins>   
> Internet is the hardware part - it is a collection of computer networks connected through either copper wires, fiber-optic cables or wireless connections 

<ins>Applications built on top of Internet</ins>    
> World Wide Web, Electronic Email, Telnet, File Transfer(FTP)    
    
> Internet is the infrastructure, WWW and others are services build on top of the infrastructure    

<ins>World Wide Web</ins>   
> World Wide Web can be termed as the software part – it is a collection of web pages connected through hyperlinks and URLs  
  
> interconnected system of public webpages accessible through the Internet  

> HTML, HTTP, URI are the fundamental technologies of WWW   

The working of the world wide web is based on the client-server model, A web server is a software and hardware that uses HTTP (Hypertext Transfer Protocol) and other protocols to respond to client requests made over the World Wide Web    

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
Protocols : DHCP, DNS, HTTP, SMTP, FTP, TELNET, SSH
```

It is combination of three layers, Application, Presentation and Session layer

> The application layer isn't an application, Instead, it's a component within an application        

> that manages how data is sent to and received from other devices, It's an abstraction layer service that hides the rest of the program from the transmission             

The Application layer uses Transport layer and any levels below it to communicate with or transfer data to a remote host    

[HTML, HTTP, URI are fundamental technologies of WWW](https://github.com/sushilsridhar/cs-fundamentals/tree/main/cn#computer-networks)

[HTTP is Client-Server architecture protocol](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/APP_LAYER_ARCHITECTURE.md)

[HTTP is Stateless protocol](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/HTTP.md)   

[HTTP internally uses TCP Connection](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/TCP.md)

[HTTPS uses crytographic algorithms like SSL and TLS for security](https://github.com/sushilsridhar/cs-fundamentals/tree/main/cn/HTTP.md#https)

# Transport Layer     

```
Job       : logical communication between the processes running on different hosts
Protocol  : Transmission Control Protocol (TCP), User Datagram Protocol (UDP)
```
The transport layer mainly deals with process to process(running on different hosts) communication and             
performs the port addressing, the addition of a port number to the header of the data       

[TCP is Stateful protocol](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/TCP.md)            

[TCP is reliable and connection oriented](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/TCP.md#reliable-and-connection-oriented)            

[TCP three way handshake]()             

[Break data into segments](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/TCP.md#tcp-segmentation)             

[Process to Process communication on different host]()            

[UDP is unreliable and connectionless](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/TCP.md#user-datagram-protocol)


# Network

The network layer is the third layer of the OSI model which provides communication between hosts of different networks. The network layer divides the data received from the transport layer in the form of packets. The network layer provides two ways of communication namely - connection-oriented and connection-less.

The network mainly deals with logical communication between the hosts present on the same or different network.
The network layer provides communication between hosts of different networks.

The network layer adds the logical address i.e. IP address (Internet Protocol address) if the packet crosses the network boundary.


# Internet Layer     

```
Protocol  : Internet Protocol (IP)
Job       : determine how to send the data packets from source to destination, divides data recieved into packets
```

The network layer does not guarantee the delivery of packets to the destination. There is no reliability guarantee as well.

Internet Protocol (IP) The internet protocol is a network layer protocol that is responsible for defining the rules that define how the information is sent over an internet connection from one computer to another    

Internet Protocol is responsible for gathering the addresses to which the data is to be transmitted.

he network layer divides the data received from the transport layer in the form of packets.
The network layer provides two ways of communication namely - connection-oriented and connectionless.

Logical Addressing: The network layer adds the logical address i.e. IP address (Internet Protocol address) if the packet crosses the network boundary. It helps in the proper identification of devices on the network. Hence, the network layer adds the source and destination address to the header of the packet.

Routing: Routing simply means determining the best (optimal) path out of multiple paths from the source to the destination. So the network layer must choose the best routing path for the data to travel.

If many devices are connected on the same router then there is a change of packet drop due as a router may not be able to handle all the requests. So, the network layer controls the congestion on the network as well



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
