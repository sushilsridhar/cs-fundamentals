# Threads

concurrency
is doing multiple task at same time,

it can achieved via parallelism or it can be achieved via doing task asynchronously

parallelism -,

example,

two customer coming inside hotel at same time, ordering different at same time, after 20mins, getting the food at same time

in the background we don't know how many chefs cooked the food, or only one single chef asynchronously did cooking or multiple chefs parrally cooked the food



program -> defined set of procedures or instructions to follow, it is not alive,

when it executed, it becomes alive, it is called process

run the program, it becomes process

process needs, memory and computing power

memory is RAM, measured in bytes and computing power is CPU, measured in flops (floating point operations per second) which is proportional to ghz


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





