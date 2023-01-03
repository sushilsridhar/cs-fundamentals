
# How a web page is retrieved?

<ins>DHCP</ins>   
> turn on wifi, connect to internet, it assigns computer a unique IP address

The Dynamic Host Configuration Protocol is a network management protocol that dynamically allocates a unique IP address to any device   
or node on a network so that they can communicate using IP

<ins>DNS</ins>    
> type netflix.com, get IP (browser cache, OS cache) else request goes to DNS resolver (get IP from DNS cache or else request goes further down)   

>  after getting the IP address, browser makes a HTTP request to that IP

![Screenshot 2022-12-31 at 6 30 23 AM](https://user-images.githubusercontent.com/16437905/210120359-c99ca7e3-2a61-495f-aa2d-44bdbc5f9b7c.png)


<ins>HTTP</ins>   
Once we get the IP address of the website, the browser sends an HTTP request to the server to extract the HTML webpage corresponding to the IP address, This request is sent over PORT 80 using TCP, Once the server receives this HTTP request, it responds back with an HTTP response, This HTTP response consists of the information related to the HTML page corresponding to the IP address of the website     

The browser receives the HTML information for the website along with the response and hence, it processes and displays the HTML page on the browser. Finally, the users can see a HTML page for the URL that they entered

> An HTTP request consists of 3 parts i.e. a request line, request headers, and request body

<ins>HTTP Request</ins>   
![Screenshot 2023-01-03 at 5 08 12 AM](https://user-images.githubusercontent.com/16437905/210285140-625c7164-aa21-4dbb-8dcf-87893283b71c.png)

<ins>HTTP Response</ins>   
![Screenshot 2023-01-03 at 5 08 21 AM](https://user-images.githubusercontent.com/16437905/210285143-4aede94e-2830-4de7-8f1d-1e67db468086.png)


what protocol does JDBC uses? is it http and tcp ?