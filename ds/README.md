# Java Collections

![Screenshot 2022-06-25 at 8 16 31 PM](https://user-images.githubusercontent.com/16437905/175778730-7e5b02de-5511-4cc0-bfe6-0186e42aa17e.png)



<ins>List</ins>     
```
1. ArrayList   : fast access, contiguous memory location     
2. LinkedList  : non-contiguous memory location, efficient usage of storage space, 
                 needs extra memory for node creation  

3. Vector (contains implementation of Stack)     
               : same as ArrayList, but thread safe hence slow
```

<ins>Queue</ins>     
```
1. PriorityQueue   : to create a Heap, to create a ordered queue 
```
```
Deque extends Queue interface
Deque implementations

2. LinkedList (contains implementation of Queue, Stack, ArrayDeque) 
                   : non-contiguous memory location, efficient usage of storage space, 
                     needs extra memory for node creation   
                   
3. ArrayDeque      : insert and remove from both ends of queue

```

<ins>Set</ins>     
```
check below items and update

HashSet
store unique elements and search them
TreeSet
thread safe
order by comparator/natural
LinkedHashSet
if we need ordering (insertion) of the items in a set
```

<ins>Map</ins>     
```
check below items and update

HashMap

java hashmap treemap linkedhashmap btree 

simplest way to store key-value pairs
LinkedHashMap
ordering of keys

add iterable interface and for each benefits
HashMap<String, Integer> hashmap = new HashMap<>();

for(String key: hashmap.keySet()) {
Integer i = hashmap.get(key);
}
```

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

if List\<Goods> is expected, java does not allow List\<Sand> even though Sand is subtype of Goods  

<ins>Why invariant</ins>   

lets say if java allows list of any type(different than T) as parameter to insertAll method,    
  
```
        Stack<T> items = new Stack<>();

        void insertAll(List<AnyType different than T> items) {
            filled += items.size(); // check if filled <= capacity
            this.items.addAll(items);
        }

```

at run time, java does not know what is the type(T) of List<T> is passed,   

> also at run time, object of any type can be added inside Datastructures,  

Stack\<Integer> is same as Stack\<String>, the type check happens only at compile time,      
  
<ins>Proof</ins>      
stringList holds objects of int and boolean at run time 

```
    ArrayList<Object> objList = new ArrayList<>();
    objList.add(10);
    objList.add(true);
            
    ArrayList<String> stringList = (ArrayList) objList;

    for(Object x: stringList) {
        System.out.println(x);
    }

```
> thus the stack<T> get polluted with objects of different data types at run time,    
> to enforce type safety in generics, it is made invariant   

else, 
  
java needs to explicitly check whether this type T passed in insertAll method is subtype or supertype or same type as defined in Stack<T>,   

<ins>code to show invariant </ins>   
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

# Wildcards in Java Generics

> covariant and contravariant in generics is created used wildcards 

Type parameters must match exactly, this is called invariant    

if List\<Goods> is expected, java does not allow List\<Sand> even though Sand is subtype of Goods,    
  
> to enable above scenario, generics have wildcards  

<ins>example</ins>    
in, insertAll(List<? extends T> items), List\<Sand extends Goods> is accepted, Sand is a subtype of Goods class, this is covariant, as subtypes are accepted   

<ins>code to show covariant</ins>   

```
public class Generics {
    public static void main(String[] args) {

        Truck t = new Truck();
        t.insert(new Cement());
        ArrayList<Sand> sandBags = new ArrayList<>(2);
        sandBags.add(new Sand());
        sandBags.add(new Sand());
        t.insertAll(sandBags);
        t.printStatus();
    }
  
  static class Vehicle<T> {
        Stack<T> items = new Stack<>();

        void insertAll(List<? extends T> items) {
            filled += items.size(); // check if filled <= capacity
            this.items.addAll(items);
        }

        void insert(T item) {
            filled++; // check if filled <= capacity
            items.add(item);
        }
    }

  static class Truck extends Vehicle<Goods> {}

}
```
<ins>syntax for contravariant</ins>   

List\<? super Goods> is accepted, any class which is parent of Goods is accepted, hence contravariant 

```
      void insertAll(List<? super T> items) {
            filled += items.size(); // check if filled <= capacity
            this.items.addAll(items);
        }
```

usecases for this, check this

Collections.copy
addall methods of all collections

