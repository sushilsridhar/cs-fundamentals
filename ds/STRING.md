# String

> Ordered sequence of characters    


immutable, once created can't be changed  
since it can't be changed, it can be shared 


> It is a non primitive data type, build on top of character array   

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

<ins>Where to store, String pool or Heap ?</ins> 

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

<ins>ASCII value of</ins>  

> 'a'-'A' gives 32, use this value instead of remembering ASCII values    

```
  'A' - 65
  'B' - 66
  'C' - 67
  'Z' - 90

  'a' - 97
  'b' - 98
  'c' - 99
  'z' - 122

  '0' - 48
  '1' - 49
  '9' - 57
```

# String methods  

Replace multiple white spaces with a single white space,    

```
    String s = str.trim().replaceAll("\\s+"," ");
```    

Substring method
``` 
    
  System.out.println("hello".substring(1, 5));
  System.out.println("hello".substring(-1+1, 5));

  prints ello, substring method is exclusive of start index and inclusive of end index
  also for substring method, index starts from 1 not 0


 Substring method internal working

    prints ello,
    0-1 -> prints h

    substring method is exclusive of start index and inclusive of end index
    also for substring method, index starts from 1 not 0, 
    endIndex of 5 in substring means actual index of 4 in string

    in other words,

                // 0 1 2 3 4 - string index
                // 1 2 3 4 5 - substring method index
                // h e l l o
    i-j (0-1) means, print from i+1 to j with starting index as 1

    0-1 --> 1-1 -> since startindex is from 1 for substring, h is printed
    0-5 --> 1-5 -> hello is printed
```
```
    char a = s.charAt(0);
    boolean isPresent = s.contains("asd");
    int index = s.indexOf("a");
    String[] str = s.split("");
    char[] arr = s.toCharArray();
```
# When to think of Strings? 

When n number of String objects with same value (string literals) are to be created multiple times, Java String class can save heap space by using the concept of string pool and intern, it reduces load on memory and improves performance 

<ins>Proof that Strings saves heap space</ins>  

Because of String immutability and intern pool, heap space is saved for String t1 and t2 and shared across multiple threads,    

```
    public static void main(String[] args) {
        
        Runnable r = new Runnable() {
            @Override
            public void run() {
                String t1 = "hello";
                String t2 = new String("hello").intern();
                String t3 = new String("hello");

                int a = 10;
                ArrayList<Integer> l = new ArrayList<>();
                System.out.println(Thread.currentThread().getName()+" "+
                        "t1:"+ System.identityHashCode(t1) +" "+
                        "t2:"+ System.identityHashCode(t2) +" "+
                        "t3:"+ System.identityHashCode(t3) +" "+

                        "a:"+ System.identityHashCode(a)  +" "+
                        "l:"+ System.identityHashCode(l));
            }
        };

        Thread t = new Thread(r);
        Thread t1 = new Thread(r);

        t.start();
        t1.start();
    }
    
    /*
      Thread-0 t1:2095837363 t2:2095837363 t3:1915490654 a:1980996547 l:856759141
      Thread-1 t1:2095837363 t2:2095837363 t3:696981276  a:1980996547 l:659356765
    */
```

# Disadvantages

If the use case is to edit or update the same string multiple times, since Strings are constants, instead of altering, 
new String objects are created in heap every time, wasting lot of memory space  

# Mutable Strings

<ins>String Buffer</ins>  
> thread safe   

<ins>String Builder</ins>   
> not thread safe, hence faster than String buffer    

most commonly used for string problems,   


