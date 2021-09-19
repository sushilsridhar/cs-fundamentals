# linux

Linux is kernel  
kernel is a system software within the operating system  
Unix is operating system

# How computer starts  
power on   
-> CPU on (POST - power on self test begin, basic diagnostic check) after diagnostic complete, sends signal to ROM    
-> BIOS (stored on ROM) initializes hardware before loading operating system, reads the hard drive, encounters the first piece of operating system, bootstrap loader     
-> bootstrap loader, loads the operating system and hand over the control to it    
-> operating system, it is loaded from hard drive to RAM (which is memory accessed by CPU) by bootstrap loader, OS's important functions are 1.Processor management 2.Memory management 3.Device management 4.Storage management 5.Application interface 6.User interface  
-> Every other programs started, are loaded into RAM for processing.

# SOLID principles

Single responsibility principle
- 1 method should have one responsibility
- 1 class should have one responsibility  

Open/close principle
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
