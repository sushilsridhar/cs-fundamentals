# Things to keep in mind

Don't over engineer       
DRY - Do not repeat       
Spaghetti code    
YAGNI - You aren't going to need it   



# SOLID principles

guidelines to design a better software system, 

> what is a good software system?   

extensible        
maintainable    
reusable    
easy to test        
modular (small chunks of code)    
understandable    


# SRP - Single Responsibility Principle
> 1 method should have one responsibility   

> 1 class should have one responsibility  

There should be exactly only one reason to change a particular block of code  

<ins>Why SRP? - More maintainable</ins>    
if there is change, i can change at one place, it will reflect everywhere       

if there is change related to sparrow, this change occurs where other blocks also exists,      
> retest - rebuild the unrelated code - violates SRP 


![Screenshot 2023-05-10 at 12 41 02 PM](https://github.com/sushilsridhar/cs-fundamentals/assets/16437905/a9949a8f-626b-4e94-8d61-fa33e0a38daf)

<ins>Violates SRP</ins>   

> function does more than what function name says   


![Screenshot 2023-05-10 at 12 51 29 PM](https://github.com/sushilsridhar/cs-fundamentals/assets/16437905/7ebda2f1-950a-4e0d-b145-29c0cf6b1919)

<ins>Follows SRP</ins>      

![Screenshot 2023-05-10 at 12 51 56 PM](https://github.com/sushilsridhar/cs-fundamentals/assets/16437905/d5ef0e3a-d025-4a10-a21a-8d9a0a35158f)


# OCP - Open/close principle
> open to extension (new features)

> close to modification ( should not modify already tested code, should not already mess up working code)  


<ins>Why OCP? - More easy to test</ins>     
after adding a new feature, if something breaks, we can debug only the newly added code, test only what is newly added       
the code is more modular    

<ins>Violates OCP</ins>   

![Screenshot 2023-05-10 at 4 56 24 PM](https://github.com/sushilsridhar/cs-fundamentals/assets/16437905/eceafb29-7b8d-472b-bee3-b81c898ce6af)


<ins>Solution to OCP Violation</ins>    
Abstracting behaviour using interface

![Screenshot 2023-05-10 at 5 06 46 PM](https://github.com/sushilsridhar/cs-fundamentals/assets/16437905/16c96522-0d57-4197-84e3-304ec8900410)



# Liskov substitution principle  
- None of the classes should be forced to implement any method which it is not supposed to implement  
- Objects of the parent class should be completely replaceble by child object (eg. Stack class can't extend ArrayList class, all methods in arraylist is not supported by stack, Stack implements List interface)

# Interface segregation
- Every interface should have a single responsibility
- to get different functionality, implement different interface. 
- eg. Stack class implements Serializable, Cloneable, Iterable<E>, Collection<E>, List<E>, RandomAccess
  
# Dependency inversion
- Irepo interface, implemented by SqlRepo and MongoRepo
- class Employee {
  save(IRepo irepo) { irepo.save() }; }, instead of injecting object, we are injecting abstraction
- instead of creating new SqlRepo object inside Employee, it is injected into save method
- different from dependency injection, inversion of control(Spring framework)
