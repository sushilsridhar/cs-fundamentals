# String

> It is a non primitive data type, build on top of character array   

1. immutable, once created can't be changed
2. since it can't be changed, it can be shared

<ins>Official definition</ins>  
```
The String class represents character strings  
All string literals in Java programs, such as "abc", are implemented as instances of this class 
Strings are constant; their values cannot be changed after they are created 
String buffers support mutable strings 
Because String objects are immutable they can be shared 
```       

<ins>String literals are implemented as instances of String class</ins>  
```
String a = "abc"; -> object of String class  

char c1 = "hello".charAt(1);
int len = "hello".length;
```

# How strings are stored in memory?

> String pool is a special storage inside heap memory where string literals are stored  

<ins>String interning</ins> 

```
String t = "hello"; 
```

When a string literal is created, the JVM first checks that literal in the String Constant Pool, If the literal is already present in the pool, its reference is returned and stored in the variable, 

However, if the string literal is not found, the JVM creates a new string object in the String Constant Pool and returns its reference  

> same can triggered manually by using intern method

if hello is found in string pool, it is reused else new hello object is created in string pool  

```
String t4 = new String("hello").intern();   
```

<ins>Where to store String pool or Heap ?</ins> 

| declaration | stored in | is the object same?
:---: | :---: | :---:
String t1 = "hello";                        | string pool   | same
String t2 = "hello";                        | string pool   | same    
String t3 = new String("hello");            | heap          | different
String t4 = new String("hello").intern();   | string pool   | same
String t5 = new String("hello");            | heap          | different
String t6 = new String("hello");            | heap          | different
  
<ins>code to verify</ins> 

```
   public static void main(String[] args) {

        String t1 = "hello";
        String t2 = "hello";
        String t3 = new String("hello");
        String t4 = new String("hello").intern();
        String t5 = new String("hello");
        String t6 = new String("hello");
        

        System.out.println("t1: "+ System.identityHashCode(t1));
        System.out.println("t2: "+ System.identityHashCode(t2));
        System.out.println("t3: "+ System.identityHashCode(t3));
        System.out.println("t4: "+ System.identityHashCode(t4));
        System.out.println("t5: "+ System.identityHashCode(t5));
        System.out.println("t6: "+ System.identityHashCode(t6));

        /*
            t1: 1627674070
            t2: 1627674070
            t3: 1360875712
            t4: 1627674070
            t5: 1625635731
            t6: 1580066828
         */
  }

```

# When to think of Strings? 

When n number of String objects with same value (string literals) are to be created multiple times, Java String class can save heap space by using the concept of string pool and intern, it reduces load on memory and improves performance 


# Disadvantages


# Mutable Strings

String buffer string builder



