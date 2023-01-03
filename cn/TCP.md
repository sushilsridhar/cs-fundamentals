# Transmission Control Protocol

> TCP is reliable (because connection oriented)          

<ins>Things done by TCP in Transport Layer</ins>  
```
Guaranteed delivery  -  if you want to delivery data, it will get delivered  
In-order delivery    -  the data must be received in the same sequence as it was sent by the sender   

create segments      -  recieves data from application layer and converts them to segments
port addressing      -  addition of a port number to the header of the data

flow control         - 
error control        -

```

<ins>Connection Oriented</ins>    
the connection is established and the data is sent over the connection only after the establishment of the connection

![Screenshot 2023-01-03 at 4 53 29 AM](https://user-images.githubusercontent.com/16437905/210284566-67d68bb6-b694-459f-8260-668072a5cc17.png)
![Screenshot 2023-01-03 at 4 55 08 AM](https://user-images.githubusercontent.com/16437905/210284613-53b2a994-bbe0-4907-b6ac-c4b80fd677e5.png)

![Screenshot 2023-01-03 at 4 56 49 AM](https://user-images.githubusercontent.com/16437905/210284713-7ee5d907-fdbe-482f-a5b9-ffd5e9ae52f5.png)


<ins>Guaranteed Delivery</ins>    
> TCP checks for errors, using checksum  


![Screenshot 2023-01-03 at 4 57 01 AM](https://user-images.githubusercontent.com/16437905/210284685-b604fcc0-c4f0-4040-9bd7-f3da07f7eac1.png)


# Code
read this 
https://www.scaler.com/topics/computer-network/difference-between-transport-layer-and-network-layer/
