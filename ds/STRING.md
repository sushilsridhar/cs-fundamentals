# String

> It is a non primitive data type, build on top of character array   


<ins>Official definition</ins>  
```
The String class represents character strings  
All string literals in Java programs, such as "abc", are implemented as instances of this class 
Strings are constant; their values cannot be changed after they are created 
String buffers support mutable strings 
Because String objects are immutable they can be shared 
```       

<ins>points</ins>  
1. immutable, once created can't be changed
2. since it can't be changed, it can be shared
3. stored inside string pool which is inside heap space


<ins>String literals are implemented as instances of String class</ins>  
```
String a = "abc"; -> object of String class  

char c1 = "hello".charAt(1);
int len = "hello".length;
```

String buffer string builder

string pool 
interning 

# String pool

string pool is a area inside heap memory where string literals are stored

<ins></ins>

String t4 = new String("hello").intern(); 


<ins>how strings are storage in memory?</ins> 

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

