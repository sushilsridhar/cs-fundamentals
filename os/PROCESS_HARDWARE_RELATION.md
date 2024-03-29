# Journey of Process

<ins>Step 1</ins>: Developer codes the app, and compiles the app into a file (.class, jar, war - incase of java), which is stored in hardware

<ins>Step 2</ins>: When user starts the application, the compiled code (inside a file) is moved to RAM, 
    
<ins>Step 3</ins>: Each instruction in the file is moved by CPU from RAM to core, and executed by the CPU by creating threads inside the core of CPU

> <ins>Program</ins> - a set of instructions, compiled code stored in hardware  

> <ins>Process</ins> - A program that is in running state, the compiled code is moved to RAM and CPU starts executing it using threads

<ins>Process control block (PCB)</ins>    
for every process that gets created, a PCB is created for it, it contains all the information about the process,    
the activity monitor in mac, get all details of processes from PCB,   

<ins>What a process needs?</ins>    
> memory  
> computing power 

memory is RAM, measured in bytes  
computing power is CPU, measured in flops (floating point operations per second) which is proportional to ghz 

Every process has a single thread by default, more can be created once process starts,  

[Relationship between threads and hardware](https://github.com/sushilsridhar/cs-fundamentals/blob/main/os/THREADS_HARDWARE_RELATION.md)

# Hardwares

> processor = microprocessor = CPU

> core = hardware threads     

<ins>Core</ins>     
Core is the execution unit, where the CPU executes the instructions, if the chip is dual core, it means, the system has two execution units,        
the CPU can run two threads in parrallel,       

Quad-core: CPU can run 4 threads in parrallel, this core is called hardware threads       

<ins>Quad-core Processor chip</ins>   
![quad-core](https://user-images.githubusercontent.com/16437905/199170376-586ca845-4e60-4f30-ac73-cd5fb90dff48.png)

<ins>GPU</ins>      
Graphical Processing unit, is a specialized processing unit for enhanced mathematical computation capability, ideal for computer graphics       

GPUs have 1000s of smaller cores,      
GPUs have a lot of cores (each of which is simpler than say a CPU core) because they do a lot of similar processing at the same time, repeating and brute force type of task,       

![logo](https://user-images.githubusercontent.com/16437905/200256352-988756e4-8c47-4e83-8b65-d3851ac954df.png)

<ins>RAM</ins>    
![ram](https://user-images.githubusercontent.com/16437905/199171006-46eb6efb-4061-4da3-b28c-148761986036.jpeg)

<ins>Disk storage</ins>    
![ssd](https://user-images.githubusercontent.com/16437905/199172353-87ecd905-a0e3-4137-a01d-84dfba309730.jpeg)
![hdd copy](https://user-images.githubusercontent.com/16437905/199172766-42e263ef-c282-4bff-aaf0-ea6661eefab8.png)

<ins>Microcontroller</ins>    
These are mainly used in embedded system, where all the components are fabricated within the single chip itself,    
RAM, Processor etc, are within the same single chip,    

![microcontroller_overview](https://user-images.githubusercontent.com/16437905/199241623-0211cde6-cb25-4cfc-bd8b-2cbcfec7656a.png)

example: microcontroller in a calculator (embedded system)    

![microcontroller-calculator](https://user-images.githubusercontent.com/16437905/199242241-75e0ff60-9424-4771-a6a3-e6b026607a9e.jpg)

<ins>Microprocessor and Microcontroller</ins>   

![mp-vs-mc](https://user-images.githubusercontent.com/16437905/199255122-d4379b75-f3bd-4d9d-b26c-91dffed5b63f.png)


# Tear down of MacBook Air 13' 2015

<ins>SSD</ins>    
![ssd-1](https://user-images.githubusercontent.com/16437905/199257224-6ce4eb24-d390-4fe6-bf67-38b71009fdf7.png)   
![ssd-2](https://user-images.githubusercontent.com/16437905/199257425-662716f6-a61d-4844-ae78-54424af8d1ba.png)


<ins>Processor (CPU and GPU)</ins>        
![logic board](https://user-images.githubusercontent.com/16437905/199258040-3585c8df-87f2-4dbc-8b36-013335ae470b.png)
![logic board 2](https://user-images.githubusercontent.com/16437905/199258083-559501eb-9371-448c-941f-54dac1ca7283.png)

<ins>RAM</ins>    
![ram](https://user-images.githubusercontent.com/16437905/199258147-1108bb42-8012-4a50-8439-1fda01bdf807.png)

# CHECK 
what is stored in cache l1 l2       
add hardware for l1 l2 cache
