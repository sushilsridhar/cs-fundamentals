# Hyper Text Transfer Protocol

HTTP is a stateless protocol,   

meaning, every request is independent and it will not be dependent on the previous request 

![Screenshot 2022-12-30 at 4 52 52 AM](https://user-images.githubusercontent.com/16437905/210020424-98b1419d-6a7d-4527-b06f-59fd3ac54afd.png)


<ins>HTTP Connection</ins>   

[HTTP internally uses TCP Connection](https://github.com/sushilsridhar/cs-fundamentals/blob/main/cn/TCP.md)

HTTP relies on the TCP (Transmission Control Protocol) and it works on the PORT number 80, Hence, a connection is first established (TCP connection) and then the data is transferred over this connection

> HTTP uses TCP, so TCP connection (3-way handshake) is created for connection


```
Non-Persistant Connection - for every request, create a new connection      
Persistant Connection     - multiple request, single connection 
```

![Screenshot 2023-01-02 at 6 41 55 PM](https://user-images.githubusercontent.com/16437905/210235992-a48856ca-40e2-4036-8b95-f3a947415de9.png)


# HTTPS    
> It uses cryptographic algorithms like SSL (Secure Socket Layer) and TLS (Transport Layer Security) which makes it more secure than HTTP   

HTTPS is slower than HTTP since it includes additional steps for the cryptographic algorithms

# File Transfer Protocol 

FTP is statefull protocol,        

meaning, the moment you login, ftp maintains that session and assumes the previous login data to do all the work    

req 1 and req 2, req2 is dependent on req1 and use data that was sent in req1   

