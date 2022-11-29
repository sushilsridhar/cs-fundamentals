# Computer Networks

<ins>Protocol</ins> is a set of rules that governs the transmission between two computers    

# OSI model
Open Systems Interconnection
> OSI model is a reference model/tool to actually model or trace the actual flow of how data transfers in networks 

> It is a logical representation of how the network systems are supposed to send data (or, communicate) to each other  


<img src="https://user-images.githubusercontent.com/16437905/202834366-655b09c7-67ec-4f55-a690-2149fbdc744d.png" width="500">

![osi](https://user-images.githubusercontent.com/16437905/202200438-ea1c47e3-966c-44aa-b5a9-db82375b0dce.png)


# Internet Protocol Suite - TCP/IP 
> OSI model is a reference model while TCP/IP is an implementation of OSI model

TCP/IP Model helps you to determine how a specific computer should be connected to the internet and how data should be transmitted between them 

OSI model gives guidelines on how communication needs to be done, while TCP/IP protocols layout standards on which the Internet was developed

![The-logical-mapping-between-OSI-basic-reference-model-and-the-TCP-IP-stack](https://user-images.githubusercontent.com/16437905/202834288-127fcd13-48ef-433c-b7dd-5d846f79f831.jpg)


Application layer, Presentation layer and Session layer are managed as part of application code,   
Transport layer is managed by OS, 

<ins>Application Layer</ins>    
create data that has to be transferred over network  
``` 
Protocols: 
```


<ins>Physical Layer</ins>     
The physical layer receives the frames from the Data Link Layer and generates information on bits of electrical impulses or light depending on the medium being optical or electrical and transmits them physically bit by bit

Protocols: 

```
Presentation - encrypt/decrypt data, format data   
Session      - create sessions    

Transport    - TCP, UDP (transport Protocol are used)  
Network      - IP layer (Internet Protocol layer), 
```


# IP

IPV4: 0-255 . 0-255 . 0-255 . 0-255 , 32 bits total - 2^32 combinations   
IPV6: 128bits, 2^128 combinations     

<ins>Private IP</ins>   
Router assigns different IPs to all devices connected to it,    
eg:, Computer, phone, TV - all connected to single wifi have different private IP address

<ins>Public IP</ins>    
Router has one public IP to all the devices connected to it,    
eg: Computer, phone, TV - all connected to single wifi have same Public IP address, which is used to connect to internet    

<ins>Network Address Translation</ins>     
NAT helps in reusing the private IP address, as IP address numbers are limited

![NAT](https://user-images.githubusercontent.com/16437905/203917514-e2174dcf-bb48-4002-bd53-9fab59940ebb.png)
Network address translation (NAT) is a method of mapping an IP address space into another by modifying network address information in the IP header of packets while they are in transit across a traffic routing device. The technique was originally used to bypass the need to assign a new address to every host when a network was moved, or when the upstream Internet service provider was replaced, but could not route the network's address space. It has become a popular and essential tool in conserving global address space in the face of IPv4 address exhaustion. One Internet-routable IP address of a NAT gateway can be used for an entire private network

the mapping of IP address is stored inside NAT table in router,   

![nat-table](https://user-images.githubusercontent.com/16437905/204550936-a8d54990-90f5-445d-97d6-5dc6e93f6925.png)



# MAC
any part of the system, that comes in contact with internet has MAC address
mac address - unique address in hardware of a computer to identify 
MAC addresses are used in the medium access control protocol sublayer of the data link layer. As typically represented, MAC addresses are recognizable as six groups of two hexadecimal digits, separated by hyphens, colons, or without a separator.

find out where MAC is written, is it inside ROM, add ROM photos in hardware section



# DDNS 
DNS stands for domain name system, and a dynamic DNS gives a permanent domain name to a computer, such as mybusiness.ddns.com, and automatically keeps track of that computer's IP address, even if it changes. Therefore, when someone on the outside internet wants to contact your computer, they can contact mybusiness.ddns.com, and the dynamic DNS service will know how to contact your computer. It's like having a personal assistant whose job it is to know how to reach you at all times.

dns how to deploy app with ddns, how it works, 

how dns works

how to buy static ip from ISP find out

why ipv5 does not exist


port number is unique to application running on same IP

https: 443
http : 80, what is relation between protocols and port number

# application layer

client server architecuter - centralized data,  clients consumes and server own any data
peer to peer architecture - same apps running on end devices , blockchain bit torrent, no centralized server, everyone is client as weell as server 


# HTTP 
http is stateless protocol, tcp is stateful 

it is application layer protocol, it uses TCP at transport layer


# Questions
socket vs session
check InetAddress class which is implementation of IP protocol

check the libraries of TCP IP HTTP implemenetation

network layer creates the route which will be used to transfer, you need receiver IP address for it

what is IP Protocol
