
# End to End flow

<ins>DHCP</ins>   
> turn on wifi, connect to internet, it assigns computer a unique IP address

The Dynamic Host Configuration Protocol is a network management protocol that dynamically allocates a unique IP address to any device   
or node on a network so that they can communicate using IP

<ins>DNS</ins>    
> type netflix.com, get IP (browser cache, OS cache) else request goes to DNS resolver (get IP from DNS cache or else request goes further down)   

>  after getting the IP address, browser makes a HTTP request to that IP

![Screenshot 2022-12-31 at 6 30 23 AM](https://user-images.githubusercontent.com/16437905/210120359-c99ca7e3-2a61-495f-aa2d-44bdbc5f9b7c.png)

Sending request to the server to access the webpage and receiving response 
Once we get the IP address of the website we want to access using DNS, 
the browser sends an HTTP (Hypertext Transfer Protocol) request to the server to 
extract the HTM (Hypertext Markup Language)L webpage corresponding to the IP address. 
This request is sent over PORT 80 using TCP (Transmission Control Protocol). 
Once the server receives this HTTP request, it responds back with an HTTP response. 
This HTTP response consists of the information related to the HTML page corresponding to the IP address of the website.
