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
