# Collections

# Java Generics

Using Generics it is possible to create classes that work with different data types,   
and provides type safety feature

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
