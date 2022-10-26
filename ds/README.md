# Java Collections

![Screenshot 2022-06-25 at 8 16 31 PM](https://user-images.githubusercontent.com/16437905/175778730-7e5b02de-5511-4cc0-bfe6-0186e42aa17e.png)


# Java Generics

Using Generics it is possible to create classes that work with different data types,   
and provides type safety feature at compile time  

<ins>Java 1.4</ins>  

This is allowed for backward compatibility purposes, Although it is not recommended  

```
ArrayList result = new ArrayList();
content.add(3); 
content.add("Hello"); // no error, although explicit casting should be done when retrieved
```
<ins>Java 5.0</ins>  

``` 
ArrayList<Integer> content = new ArrayList<Integer>(); 
content.add(3); // will work
content.add("Hello"); // error shown 
```
  
> purpose is to enable <ins>compile-time type check</ins>

<ins>Conventions</ins>  
T – Type  
E – Element  
K – Key  
N – Number   
V – Value    

<ins>Example</ins>  

```
LinkedList<Integer> list = new LinkedList<>();    

public class LinkedList<E> {

    private static class Node<E> {
        E data;
        Node<E> next;

        Node(E data) {
            this.data = data;
            this.next = null;
        }
    }

    public boolean add(E e) {
        linkToLast(e);
        return true;
    }
}
```

# Variance
<ins>Invariant: Type parameters must match exactly</ins>  

```
ArrayList<Integer> intArrList = new ArrayList<>();
ArrayList<Number> numArrList = intArrList; // Not ok
ArrayList<Integer> anotherIntArrList = intArrList; // Ok
```

<ins>Covariant: accept subtypes</ins>  
Arrays are covariant,       

an array of type T[] may contain elements of type T and its subtypes  
an array of type S[] is a subtype of T[] if S is a subtype of T   

```
Number[] nums = new Number[5];
nums[0] = new Integer(1); // Ok
nums[1] = new Double(2.0); // Ok
```

<ins>Contravariant: accept supertypes</ins>    


# Java Generics is invariant

Type parameters must match exactly, this is called invariant    

List\<Goods> is expected, java does not allow List\<Sand> even though Sand is subtype of Goods  

<ins>Why invariant</ins>   

lets say if java allows any list as parameter to insertAll method,    

at run time, java does not know what list is passed(what is the type of T),   
java needs to explicitly check whether this type T is subtype or supertype or same type as defined in Stack<T>,   
  
but at run time, Stack<Integer> is same as Stack<String>, it accepts any type,    
this check happens only at compile time, 

```
        Stack<T> items = new Stack<>();

        void insertAll(List<T> items) {
            filled += items.size(); // check if filled <= capacity
            this.items.addAll(items);
        }

```

```
public class Generics {
    public static void main(String[] args) {

        Truck t = new Truck();
        t.insert(new Cement());
        List<Sand> sandBags = new ArrayList<>(2);
        sandBags.add(new Sand());
        sandBags.add(new Sand());
        t.insertAll(sandBags); // -> error because java generics is invariance
        t.printStatus();
    }

    static class Goods {}
    static class Cement extends Goods {}
    static class Sand extends Goods {}
    static class Person {}
    static class Student extends Person {}

    static class Vehicle<T> {
        Stack<T> items = new Stack<>();
        int capacity = 10;
        private int filled = 0;
        
        void printStatus() {
            items.forEach(t -> System.out.println(t));
        }

        void insertAll(List<T> items) {
            filled += items.size(); // check if filled <= capacity
            this.items.addAll(items);
        }

        void insert(T item) {
            filled++; // check if filled <= capacity
            items.add(item);
        }
        
        T unload () {
            T item = items.pop();
            filled--; // check if filled >= 0
            return item;
        }
    }

    static class SchoolBus extends Vehicle<Person> {}
    static class Truck extends Vehicle<Goods> {}
}
```


<ins>Type Erasure</ins> 


<ins>wildcards</ins>    




