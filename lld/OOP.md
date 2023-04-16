# Object Oriented Programming

> The fundamental principle of OOP is Abstraction   

<ins>Abstraction</ins> - making something as abstract, representing something as idea     

turning on the video in the interview in zoom, you don't know how video is transmitted, you just know the idea that if you click the video button, the other person can see the video, you just use it and the internal working is abstracted out

the target is to achieve abstraction    

> representation of a complex system in terms of idea (entities - data & behaviour)   
  
as a client we don't need to care about how a idea works internally   

<ins>3 pillars of OOP</ins>  

the 3 pillars are the way to achieve the core principle abstraction       

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
Interface         | Pure abstraction, and enforces a certain behaviour to be implemented
Abstract class    | Partial abstraction

protected access modifier - is accessible inside package and by subclasses outside the package   

# Encapsulation

> achieves abstraction by using access modifiers

think of a medicine capsule,    

a class encapsulates the data and behaviour of the entity together

1. stores data and behaviour of an idea together
2. hides unneccessary details to the outside world
3. only expose what we want to clients using access modifiers


# Inheritance  

> achieves abstraction - the implementation of the behaviours in base class is abstracted out and unknown to the outside world

1. OOP allows us to design hierarchial systems with categorisation         
2. reduces duplicate code        


```
abstract class Car {
    abstract void startEngine();
}

class PetrolCar extends Car {

    private void checkFuel() {}

    public void startEngine() {
        checkFuel();
        // do other things
    }
}


Car pc = new PetrolCar();
pc.startEngine();

```

![inheritance](https://user-images.githubusercontent.com/16437905/232023869-74c64d54-8374-447c-9573-f3ecb8ca6f1b.png)


# Polymorphism  

> Achieves abstraction by abstracting out what object is being passed

```
public static void main(String[] args) {

        TA ta = new TA("TA", "ta@scaler.com");
        Mentor mentor = new Mentor("Mentor", "mentor@scaler.com");
        Student student = new Student("Student", "student@scaler.com");

        printName(ta);
        printName(mentor);
        printName(student);
}


// Abstraction - this method is abstracted out from object being passed
public static void printName(User user) {
    System.out.println(user.getName());
}

```

1. ability of somethings to have multiple forms   
2. compile time polymorphism - method overloading - (compiler knows which methods to call at compile time itself)   
3. run time polymorphism - can be achieved using method overiding   


<ins>Method overloading</ins>: multiple methods inside the same class, having the same name but different arguments or same arguments in different order,   happens in same class         

<ins>Method overiding</ins>: overide the method with same signature with different implementation in child class, happens in child class, the access modifier of overiding method should be same or more freedom than parent method, name params and return type should match parent class method   

![polymorphism](https://user-images.githubusercontent.com/16437905/232064474-bf453e35-dd76-484b-b75b-3426244d7360.png)

# Interface  
> Pure abstraction    

> guides the behaviour of a group of entities           

enforces a certain behaviour to be implemented, but how to implement is abstracted    

![interface](https://user-images.githubusercontent.com/16437905/232286695-5f7a5930-80ef-4106-b180-734a2fe9c06f.png)


<ins> Interface represents a abstract idea, and it enforces a certain behaviour to be implemented</ins>    

```
interface Deque<E> {
    
    void push(E e);
    
    E pop();

    E peek();
}


Deque<Integer> stack = new LinkedList<>();
Deque<Integer> stack = new ArrayDeque<>();

```

<ins>JVM example for interface</ins>   
JVM is a specification, the implementation is given by oracle, openJDK etc, specification enforce a particular behaviour to be implemented, the various implementations follow this guideline, so that it can be swapped, we can remove oracle jdk and replace it with openJDK to run the same java program,    

Interface is similiar to specification, eg: defining the db related methods as interface, so that the implementation can be swapped if required ( changing to another db)   

> does java support multiple inheritance, for classes - no , for interfaces - yes   

<ins>Marker interface</ins>   
> has no methods, it just a marker to give run-time type information about objects to compiler and jvm   

Serializable : If a class implements the Serializable interface, we can serialize or deserialize the state of an object of that class

```
class Employee implements Serializable  


Employee emp =new Employee(1187345,"Andrew"); 

//Creating stream and writing the object    
FileOutputStream fout=new FileOutputStream("employee_data.txt");    
ObjectOutputStream out=new ObjectOutputStream(fout);    
out.writeObject(emp);    

```

Cloneable : If we do not implement the Cloneable interface in the class and invokes the clone() method, it throws the ClassNotSupportedException.

```
class Product implements Cloneable   

Product p2 = (Product) p1.clone();  
```

<ins>Functional interface</ins>   
has only one abstract method, it enables functional programming and parallel processing

```
@FunctionalInterface
public interface Runnable {}

@FunctionalInterface
public interface Callable<V> {}

```

# Abstract class

It has attributes and behaviours, but not sure if some behaviours can be common to all childs, in that case declare the behaviour as abstract    



