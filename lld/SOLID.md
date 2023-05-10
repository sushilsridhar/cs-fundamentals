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

if there is change related to sparrow, this change occurs where other blocks also exists,      
> retest - rebuild the unrelated code - violates SRP 


![Screenshot 2023-05-10 at 12 41 02 PM](https://github.com/sushilsridhar/cs-fundamentals/assets/16437905/a9949a8f-626b-4e94-8d61-fa33e0a38daf)


# Open/close principle
- open to extension (new features)
- close to modification ( should not modify already tested code, should not already mess up working code)  

Liskov substitution principle  
- None of the classes should be forced to implement any method which it is not supposed to implement  
- Objects of the parent class should be completely replaceble by child object (eg. Stack class can't extend ArrayList class, all methods in arraylist is not supported by stack, Stack implements List interface)

Interface segregation
- Every interface should have a single responsibility
- to get different functionality, implement different interface. 
- eg. Stack class implements Serializable, Cloneable, Iterable<E>, Collection<E>, List<E>, RandomAccess
  
Dependency inversion
- Irepo interface, implemented by SqlRepo and MongoRepo
- class Employee {
  save(IRepo irepo) { irepo.save() }; }, instead of injecting object, we are injecting abstraction
- instead of creating new SqlRepo object inside Employee, it is injected into save method
- different from dependency injection, inversion of control(Spring framework)
