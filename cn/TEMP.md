
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



# Questions
socket vs session
check InetAddress class which is implementation of IP protocol

check the libraries of TCP IP HTTP implemenetation

network layer creates the route which will be used to transfer, you need receiver IP address for it

what is IP Protocol


# Circuit and packet switching

circuit switching     

Circuit switching is a type of network configuration in which a physical path is acquired and set aside specifically for the purpose of connecting two endpoints in a network for the duration of a dedicated connection. Circuit switching is employed by typical voice phone services. Using different network devices, 
 dedicated communication channel is set up between the sender and the receiver. Due to the dedicated circuit, there is extremely little chance of data loss or error but a lot of bandwidth is lost because other senders cannot utilise the same channel when a transmission is going on.
 The main disadvantage is that since it uses a dedicated channel, it remains occupied and can't be used for other uses.
This results in wastage of bandwidth, and resources can't be completely utilized.

Analog telephone networks

packet switching
Packet switching divides data into smaller units called packets or blocks and transmits them across digital networks.

In packet switching, the message is first divided into data packets and then transmitted. It is connectionless, as it doesn't require a dedicated communication channel. These data packets are then grouped at the receiver's end to obtain the actual data or message.

Data packets can often be lost. Hence, packet switching is not reliable.
It is not preferred for transmissions with constant usages, such as voice calls.


Due to the utilization of shared physical links, there is the possibility of network security vulnerabilities.

VoIP uses packet switching instead of circuit switching. This means that packets are sent from the speaker to the listener only when someone actually says something. With traditional phone systems, a two-way connection is constantly maintained


In LTE (4G) the entire network uses packet switching and has no capability for circuit switched network support. As a result, the voice and SMS services must be moved over to a packet switched network when using the LTE (4G) networ

VoIP stands for Voice over internet protocol whereas VoLTE stands for Voice over LTE. By VoIP, we mean the sending of voice data from one place to the other through the internet. VoIP is usually used on computers when connected to the internet. Sending voice data through Skype is an example of VoIP

UDP (User Datagram Protocol ) protocol is used for transmission of actual VoLTE user data packets.
