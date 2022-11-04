# Operating System

From user perspective, it is an interface between hardware and user   

> OS provides APIs for application developers, to access hardware (memory, input, ouput) 

> OS is a resource manager (manages resources without conflict)   

![Screenshot 2022-11-01 at 11 01 42 AM](https://user-images.githubusercontent.com/16437905/199165714-8c8ceec4-7b67-4fce-93e8-c34afcc3cb1f.png)


# Types

<ins>Uni programming os</ins>: runs only one program at a time, eg: ATM machine (which runs embedded windows xp), smart devices        
<ins>Multi programming os</ins>: runs more than one program at the same time, eg: os on pc, laptops   

<ins>sub-type of multi programming os</ins>     
single user: personal laptops, smart phones   
multi user: cloud instances, different users have virtual machines setup within the same system, but for the user, it acts like a individual machine in itself

![Screenshot 2022-11-01 at 5 10 54 PM](https://user-images.githubusercontent.com/16437905/199224991-13e57b04-22c8-4f4b-b626-776550b7aaf3.png)

# I/O bound process  

when a process is I/O bound, it utilizes the CPU the least as compared to CPU bound process likes image processing, batch jobs,    
printing, document applications are I/O bound   

<ins>Interrupt</ins>    
When a process wants to do an I/O operation, it raises an interrupt to signal the CPU, the CPU transfers the control to I/O processing,     
and waits for the I/O to complete,    

<ins>CPU Scheduling</ins>   
durning this time, the CPU is free to do other tasks, which can be done using CPU Scheduling    

<ins>Pre-emptive OS</ins>      
pausing or switching of programs before its completion - CPU Scheduling is possible in Pre-emptive OS    

<ins>Non pre-emptive OS</ins>    
OS can not switch or pause a program once it has started



