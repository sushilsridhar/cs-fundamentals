# What happens before threads?
<ins>Program</ins> - defined set of procedures or instructions to follow, it is not alive   
<ins>Process</ins> - when it is executed, it becomes alive, it is called process

long story - [Journey of Process](https://github.com/sushilsridhar/cs-fundamentals/blob/main/os/PROCESS_HARDWARE_RELATION.md)    
in short - run the program, it becomes process, process creates threads to execute instructions  


# Threads

> A unit of CPU execution

<ins>example</ins>    
When letters are typed in word processor software, there are multiple tasks which happens at the same time,     
grammer check, spelling check, autosave, display to UI, suggestions, check for updates, all these can be run parrallely,    

> all threads have their own stack memory and share a common heap memory 

![Screenshot 2022-11-07 at 12 57 21 PM](https://user-images.githubusercontent.com/16437905/200250949-291ae0aa-d461-4458-8230-f9221e82333b.png)


<ins>Data sharing</ins>   
all threads inside a process share a common heap space, processes can't share data with other processes, IntelliJ can't share data with Ms Word,    
but processes can communicate with eachother, which is called IPC (Inter Process Communication)


# check below items

thread -> sequence of instructions sent to RAM, it has no memory, it inside the process and uses process memory which is shared

process has memory and thread, thread is a sequence of instructions recieved from process, which is sent to RAM for execution

all threads inside the process, have access to same memory inside the process

hardware and software threads are there


software threads run on hardware thread, hardware threads runs on CPU

executor service framework in java, check this


hardware thread is the Core, if the number of cores is 4, it means, the number of hardware threads is 4, it is fixed when you buy a CPU


we can't create hardware threads, but we can create software threads in java


ideally, in real world create threads with executors in java, and fix the thread pool size according to number of cores,

runnable functions are the tasks

separate the task from the threads is very important

Runnable classes holds the instructions, is the object to hold the instructions/task, which can be passed to the executors


blocking queue is used to create the threads pool concept


# Concurrency

concurrency
is doing multiple task at same time,

it can achieved via parallelism or it can be achieved via doing task asynchronously

parallelism -,

example,

two customer coming inside hotel at same time, ordering different at same time, after 20mins, getting the food at same time

in the background we don't know how many chefs cooked the food, or only one single chef asynchronously did cooking or multiple chefs parrally cooked the food









