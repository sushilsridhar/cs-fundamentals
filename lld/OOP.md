# Object Oriented Programming

> The fundamental principle of OOP is Abstraction   

<ins>Abstraction</ins> - making something as abstract, representing something as idea     
representation of a complex system in terms of idea (data & behaviour)   

<ins>3 pillars of OOP</ins>   
1. Encapsulation    
2. Inheritance      
3. Polymorphism   

<ins>Basic OOP</ins>    
| terminology | explanation
:---: | :---:
Class             | Blueprint
Object            | Real world entity
Constructor       | default, custom, copy constructor 
Shallow copy      | point to same address
Deep copy         | creates new object (no sharing of object)
Access modifiers  | public, default, private, protected, classes can have only public or default modifier    
Super keyword     | allows access to parent class members from child class (attributes, methods and constructors) 

**<ins>Encapsulation</ins>**  
1. stores data and behaviour of an idea together
2. hides unneccessary details to the outside world
3. only expose what we want to clients using access modifiers

**<ins>Inheritance</ins>**    
1. OOP allows us to design hierarchial systems with categorisation         
2. reduces duplicate code        

**<ins>Polymorphism</ins>**   
1. ability of somethings to have multiple forms   
2. compile time polymorphism - method overloading - (compiler knows which methods to call at compile time itself)   
3. run time polymorphism - can be achieved using method overiding   


<ins>Method overloading</ins>: multiple methods inside the same class, having the same name but different arguments or same arguments in different order,   happens in same class         

<ins>Method overiding</ins>: overide the method with same signature with different implementation in child class, happens in child class, the access modifier of overiding method should be same or more freedom than parent method, name params and return type should match parent class method   


**<ins>Interface</ins>**   
> guides the behaviour of a group of entities           

> does java support multiple inheritance, for classes - no , for interfaces - yes   

JVM is a specification, the implementation is given by oracle, openJDK etc, specification enforce a particular behaviour to be implemented, the various implementations follow this guideline, so that it can be swapped, we can remove oracle jdk and replace it with openJDK to run the same java program,    

Interface is similiar to specification, eg: defining the db related methods as interface, so that the implementation can be swapped if required ( changing to another db)   

<ins>Marker interface</ins>: has no methods, it just a marker to give run-time type information about objects to compiler and jvm   

Serialization enables us to save the state of an object and recreate the object in a new location

<ins>Functional interface</ins>: has only one abstract method


**<ins>Abstract class</ins>**   
It has attributes and behaviours, but not sure if some behaviours can be common to all childs, in that case declare the behaviour as abstract    



