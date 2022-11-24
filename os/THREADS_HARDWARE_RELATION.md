# What happens before threads?
<ins>Program</ins> - defined set of procedures or instructions to follow, it is not alive   
<ins>Process</ins> - when it is executed, it becomes alive, it is called process

long story - [Journey of Process](https://github.com/sushilsridhar/cs-fundamentals/blob/main/os/PROCESS_HARDWARE_RELATION.md)    
in short - run the program, it becomes process, process creates threads to execute instructions  


# Threads

> A unit of CPU execution

A stream of instructions are sent to CPU, A thread is a single instruction that is executed

<ins>example</ins>    
When letters are typed in word processor software, there are multiple tasks which happens at the same time,     
grammer check, spelling check, autosave, display to UI, suggestions, check for updates, all these can be run parrallely,    

> all threads inside a process have their own stack memory and share a common heap memory 

![Screenshot 2022-11-07 at 12 57 21 PM](https://user-images.githubusercontent.com/16437905/200250949-291ae0aa-d461-4458-8230-f9221e82333b.png)


<ins>Data sharing</ins>   
all threads inside a process share a common heap space, processes can't share data with other processes, IntelliJ can't share data with Ms Word,    
but processes can communicate with eachother, which is called IPC (Inter Process Communication)


# Single core vs multi-core CPUs

> Core is the execution unit of the CPU, where software threads are executed     

> Core is called the hardware threads, which is physical and fixed in a computer

each core is independent and can execute different threads at the same time

![Screenshot 2022-11-07 at 1 09 11 PM](https://user-images.githubusercontent.com/16437905/200252697-02d9ee5e-6093-4483-8985-637cea8985f4.png)

# Concurrency

A system having multiple software threads in different stages of execution at the same time, not necessarily making progress in parrallel,  

<ins>example</ins>    
A process in single core CPU, there can be many software threads, but since there is only one hardware thread, multiple threads may run in the core taking turns, but not at the same time, this is called concurrency   

![Screenshot 2022-11-07 at 1 16 06 PM](https://user-images.githubusercontent.com/16437905/200253965-50de05b0-4a20-4c7e-8d22-71b7af1f508d.png)

# Parallelism

> Concurrency + progress in parallel

multiple software threads executing on different hardware threads at the same time, is called Parallelism

![Screenshot 2022-11-07 at 1 17 30 PM](https://user-images.githubusercontent.com/16437905/200254204-04fc163e-5ae4-460a-85fd-340d74817797.png)

![Screenshot 2022-11-07 at 1 18 03 PM](https://user-images.githubusercontent.com/16437905/200254311-f68a3220-bb0d-408c-8f65-48c9b46caa47.png)


# How to write multi-threaded program?

<ins>Create a task that needed to be run parallely</ins>    
main thread is the default thread, order in which the multiple threads run is decided by CPU scheduling algorithm   

Runnable functions are the tasks    
Runnable classes holds the instructions, it is the object that hold the instructions/task, which can be passed to the executors

```
public class TestThread {
    public static void main(String[] args) {

        System.out.println(Thread.currentThread().getName()+" hello world");
        Task task = new Task();
        Thread t = new Thread(task);
        t.start();
        System.out.println(Thread.currentThread().getName()+" hello world");
    }
}

class Task implements Runnable {

    @Override
    public void run() {
        System.out.println(Thread.currentThread().getName()+" hello world");
    }
}
  
main hello world
main hello world
Thread-0 hello world
  
```







