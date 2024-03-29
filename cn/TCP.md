# Transmission Control Protocol

> TCP is stateful protocol    

> TCP is reliable (because connection oriented)          

<ins>Things done by TCP in Transport Layer</ins>  
```
Guaranteed delivery  -  if you want to delivery data, it will get delivered  
In-order delivery    -  the data must be received in the same sequence as it was sent by the sender   

create segments      -  recieves data from application layer and converts them to segments
port addressing      -  addition of a port number to the header of the data

flow control         -  data is transmitted at a rate that is accepttable for both sender and 
                        receiver by managing data flow, 
                        using sliding window protocol to provide flow control
                        
error control        -  detecting and discarding corrupted packets, 
                        tracking of lost and discarded packets and re-transmit them,
                        these are done using checksum
```

# Reliable and Connection Oriented    
the connection is established and the data is sent over the connection only after the establishment of the connection,   

uses three way handshake and    
establishes a virtual path before transmitting the data         

![Screenshot 2023-01-03 at 4 53 29 AM](https://user-images.githubusercontent.com/16437905/210284566-67d68bb6-b694-459f-8260-668072a5cc17.png)
![Screenshot 2023-01-03 at 4 55 08 AM](https://user-images.githubusercontent.com/16437905/210284613-53b2a994-bbe0-4907-b6ac-c4b80fd677e5.png)

![Screenshot 2023-01-03 at 4 56 49 AM](https://user-images.githubusercontent.com/16437905/210284713-7ee5d907-fdbe-482f-a5b9-ffd5e9ae52f5.png)


<ins>Guaranteed Delivery</ins>   

> checksum is used for error detection    

Detecting and discarding corrupted packets,   
Tracking of lost and discarded packets and re-transmit them 

![Screenshot 2023-01-03 at 4 57 01 AM](https://user-images.githubusercontent.com/16437905/210284685-b604fcc0-c4f0-4040-9bd7-f3da07f7eac1.png)

# Three way handshake (SYN - SYN ACK - ACK)

before data transmission, connection is established using three way handshake    

![Screenshot 2023-01-09 at 6 00 27 PM](https://user-images.githubusercontent.com/16437905/211308427-b6d4224d-4dd1-4ef6-ac8e-23f9bbb9d9d0.png)

![Screenshot 2023-01-09 at 6 12 34 PM](https://user-images.githubusercontent.com/16437905/211310626-26e7e23e-8946-4ad1-add2-ce07417245fd.png)

1. establish connection using three way handshake

> SYN - SYN ACK - ACK

2. Sending of data packets In the second step, 

the data packets along with the sequence number are sent from the first computer system (client), The second computer (server) responds to these sent packets by sending an acknowledgment or ACK, This acknowledgment bit keeps on increasing with the number of packets sent this ACK bit helps to keep track of three things,    

the successfully received packets,    
the lost packets, and   
the packets which were accidentally sent twice    

3. Closing the connection

> FIN - FIN ACK - ACK

send FIN bit, recieve FIN ACK, send ACK bit - connection get closed       

<ins>Congestion Control</ins>   
Congestion means the amount of data transferred in the network. So, the transmission control protocol also accounts for the level of congestion and sends the packets accordingly   

<ins>Stream-oriented data transfer</ins>    
The transmission control protocol creates a virtual circuit or tube in which the data is exchanged in the form of a stream of bytes

# TCP Segmentation

<ins>Sequence number</ins> is a field of 32 bit that will define the number assigned to data first byte contained in segment    
<ins>Acknowledgement number</ins> is a 32 bit field that describe the next byte that receiver is looking forward to receive next from sender    

<ins>Checksum</ins> 16-bit field contains checksum and used for error detection   

using these, in-order delivery is maintained    

![Screenshot 2023-01-09 at 10 00 20 AM](https://user-images.githubusercontent.com/16437905/211241436-3043611a-c7dc-4028-8b47-8517219f513d.png)


<ins>At the sender’s side</ins>       
At the sender's end, transport layer collect data from application layer i.e message and performs segementation to divide the message into segments and then adds the port number of source and destination in header and send that message to network layer 

<ins>At the receiver’s side</ins>        
At the receiver's end, transport layer collects data from network layer and then reassembles the segmented data and identifies port number by reading its header to send that message to appropriate port in the session layer 

reassembling of segments is done using sequence number in the header

![Screenshot 2023-01-09 at 10 35 34 AM](https://user-images.githubusercontent.com/16437905/211244026-bbd85186-09dc-4be2-8af7-a3cc754eb308.png)

# Code

<ins>Process to Process communication on different host</ins>   
Transport Layer uses a port number to deliver the segmented data to the correct process amongst the multiple processes that are running on a particular host, A port number is a 16-bit address used by transport layer to identify any client-server program   


# User Datagram Protocol

> Connection less protocol and Unreliable protocol    

> basic end-to-end transmission of data

because of not needing connection, the header size of UDP data packet is small, hence fast

non sequenced data transmission functionality, speed and size are more important than reliability and security

UDP can identify that an error has happened, but UDP does not identify which packet has been lost (only error detection not error control)    

![Screenshot 2023-01-09 at 10 39 28 AM](https://user-images.githubusercontent.com/16437905/211244359-16d8da3b-b8f8-45fc-9780-89dc7dee88cf.png)

UDP protocol is generally used for real-time applications that do not allow uneven delays between received message sections, 

> UDP is used by DNS, DHCP for transport layer
