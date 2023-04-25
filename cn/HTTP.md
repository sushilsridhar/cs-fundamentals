# Hyper Text Transfer Protocol

> HTTP is a stateless protocol,   

meaning, every request is independent and it will not be dependent on the previous request 

![Screenshot 2022-12-30 at 4 52 52 AM](https://user-images.githubusercontent.com/16437905/210020424-98b1419d-6a7d-4527-b06f-59fd3ac54afd.png)

however, when the user log in, the server returns a token in form of a cookie, that cookie is stored in the browser,    

this cookie is added to every other request the client makes, still HTTP is stateless,    
as it doesn't use the data that was sent in previous request and is independent of previous request    

<ins>HTTP Connection</ins>   

[HTTP internally uses TCP Connection](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/TCP.md)

> HTTP uses TCP, so TCP connection (3-way handshake) is created for connection

HTTP relies on the TCP (Transmission Control Protocol) and it works on the PORT number 80, Hence, a connection is first established (TCP connection) and then the data is transferred over this connection


<ins>Types of HTTP Connection</ins>     
```
Non-Persistant Connection - for every request, create a new connection      
Persistant Connection     - multiple request, single connection 
```

![Screenshot 2023-01-02 at 6 41 55 PM](https://user-images.githubusercontent.com/16437905/210235992-a48856ca-40e2-4036-8b95-f3a947415de9.png)

> An HTTP request consists of 3 parts i.e. a request line, request headers, and request body

<ins>HTTP Request</ins>   
![Screenshot 2023-01-03 at 5 08 12 AM](https://user-images.githubusercontent.com/16437905/210285140-625c7164-aa21-4dbb-8dcf-87893283b71c.png)

<ins>HTTP Response</ins>   
![Screenshot 2023-01-03 at 5 08 21 AM](https://user-images.githubusercontent.com/16437905/210285143-4aede94e-2830-4de7-8f1d-1e67db468086.png)

# HTTPS  
> HTTPS uses TCP in transport layer along with TLS to make the transport layer connection secure        

> Cryptographic algorithms like SSL (Secure Socket Layer) and TLS (Transport Layer Security) are used   

HTTPS is slower than HTTP since it includes additional steps for the cryptographic algorithms

![ssl](https://user-images.githubusercontent.com/16437905/210364726-94a43147-7367-4c94-a0de-e61bcb53b84f.png)

> TLS is the successor of SSL   

![https](https://user-images.githubusercontent.com/16437905/210365140-cba5eaa7-57ed-46d4-96c9-78e4aa921b0f.png)


```
how TLS works?

read this and update

https://anushadasari.medium.com/the-https-protocol-explained-under-the-hood-c7bd9f9aaa7b
https://medium.com/@isuruj/how-does-https-actually-work-b8c569f72f66
https://medium.com/geekculture/https-can-you-explain-how-it-works-c45a9ff6a00c
https://medium.com/@aswaikar123/what-is-http-and-https-learn-the-basics-of-http-in-5-minutes-5629be69a6ec

```

Symmetric cryptography - same key used to encrypt and decrypt - AES DES 3DES      
Asymmetric cryptography - public and private key - key generating mechanism RSA DSA     

world's unbreakable encryption algorithm is OTP (one time pad) cipher       

RSA is default key generation algorithm for SSH protocol

# Code

# File Transfer Protocol 

> FTP is statefull protocol,        

meaning, the moment you login, ftp maintains that session and assumes the previous login data to do all the work    

req 1 and req 2, req2 is dependent on req1 and use data that was sent in req1   

The File Transfer Protocol (FTP) is designed to facilitate bi-directional transfer of files and records between hosts on a TCP/IP network, Unlike HTTP, the 

> FTP protocol is stateful: the client establishes a Control Connection for the duration of an FTP session that typically spans multiple data transfers 

FTP uses a separate TCP connection for data transfer, Commands are issued and acknowledged over the Control Connection, a TCP connection to well-known port 21. If the user issues a command that requires a response more elaborate than a one-line response code, a Data Connection is established between the client and the server, The response data—the contents of a file or a directory listing—is sent over that data connection     

![Screenshot 2023-01-09 at 5 51 33 AM](https://user-images.githubusercontent.com/16437905/211226174-99e2c879-4607-4764-8179-208f17511df1.png)

