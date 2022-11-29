# Design 
<ins>HLD</ins> - infrastructural layers    
<ins>LLD</ins> - the machines at different infrastructural layers are same, but the software running in the machines are different,     
how the software is implemented?        

# Programming paradigm

<ins>Procedural programming</ins>   
> Actions are performed on real world Entities, all actions are defined as procedures in code 

We define procedures and call them in a series of sequential steps, Procedures, also known as routines, subroutines, or functions, simply contain a series of computational steps to be carried out, It is about writing a list of instructions to tell the computer what to do step by step      

we call getAccount, transfer, deposit procedures in a particular sequence to properly get desired results,    

![procedure](https://user-images.githubusercontent.com/16437905/204455706-a7d24ba3-1ad2-454b-87cf-b7bf1b1df815.png)


> changing one function in procedural languages can cause a cascade of bugs that can be difficult to trace back         

> Object-oriented programming (OOP) and functional programming were developed relatively recently to avoid the spaghetti code problem 


<ins>Object oriented programming</ins>    
> Entities perform Actions, Entities have attributes and behaviours  

They model the real world entities, we encapsulate the attributes and behaviours of the entity inside the class,    

![oop](https://user-images.githubusercontent.com/16437905/204456497-59c6811a-076f-47e7-8f41-bc44b900cfe3.png)



<ins>Functional programming</ins> -     



A functional language (ideally) allows you to write a mathematical function, i.e. a function that takes n arguments and returns a value.
 that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.
 
 In FP, functions are treated as data, meaning you can use them as parameters, return them, build functions from other functions, and build custom functions. Functions in FP have to be pure functions, they should avoid shared state, and side effects and data should be immutable.
 
 This involves a focus on creating code that avoids changing state and mutating data.

instead of implementing an entire class for performing a standalone action, we simply implemented a function.

However in functional programming data itself is code to other piece of code. Everything in functional programming revolves around pure functions where to achieve a task function is being called which internally may call another function.
The principles of functional programming are centered around the idea of pure functions .

functions return the same output for a given set of inputs 
This means functions are not allowed to use any global variable or context. Every time in every case for same inputs same output will be returned.

custom comparator
Passing custom logic to handle the ordering of elements,
```
 PriorityQueue<Points> minHeap = new PriorityQueue<>((p1, p2) -> {
            if(p1.getDistance() > p2.getDistance()) {
                return 1;
            } else if(p1.getDistance() < p2.getDistance()) {
                return -1;
            }
            return 0;
        });

```
# Object Oriented Programming

> The fundamental principle of OOP is Abstraction   

<ins>Abstraction</ins> - making something as abstract, representing something as idea     
representation of a complex system in terms of idea (data & behaviour)   

<ins>3 pillars of OOP</ins>   
1. Encapsulation    
2. Inheritance      
3. Polymorphism   

