
# Java Virtual Machine     
The Java Virtual Machine (JVM) is the virtual machine that runs the Java bytecodes. The JVM doesn't understand Java source code; that's why you need compile your *.java files to obtain *.class files that contain the bytecodes understood by the JVM.        

It's also the entity that allows Java to be a "portable language" (write once, run anywhere). Indeed, there are specific implementations of the JVM for different systems (Windows, Linux, macOS), the aim is that with the same bytecodes they all give the same results.

> JDK JRE JVM all are platform dependent  

> Java code, byte code are platform independent               

```
JVM - runs the bytecode      
JRE - JVM + Java Packages Classes(like util, math, lang, awt,swing etc) + runtime libraries     
JDK - JRE + compiler and debugger + things needed for development
```
![jdk-jre-jvm](https://user-images.githubusercontent.com/16437905/203471701-0a03afb1-4188-41d0-8c99-694b5233611d.png)

# Java code to Bytecode 

.class file contains the bytecode that will be executed and converted to machine code by JVM - check what is machine code  

[List of Java Bytecode instructions](https://en.wikipedia.org/wiki/List_of_Java_bytecode_instructions)

<ins>HelloWorld.java</ins>    
```
public class HelloWorld {
    public HelloWorld() {}
    
    public static void main(String[] args) {

        int a = 1;
        int b = 2;

        int c = a + b;
        System.out.println("Hello World :D");
        System.out.println(c + 5);
    }
}
```
<ins>HelloWorld.class</ins>  
```
// class version 52.0 (52)
// access flags 0x21
public class HelloWorld {

  // compiled from: HelloWorld.java

  // access flags 0x1
  public <init>()V
   L0
    LINENUMBER 1 L0
    ALOAD 0
    INVOKESPECIAL java/lang/Object.<init> ()V
    RETURN
   L1
    LOCALVARIABLE this LHelloWorld; L0 L1 0
    MAXSTACK = 1
    MAXLOCALS = 1

  // access flags 0x9
  public static main([Ljava/lang/String;)V
   L0
    LINENUMBER 4 L0
    ICONST_1
    ISTORE 1
   L1
    LINENUMBER 5 L1
    ICONST_2
    ISTORE 2
   L2
    LINENUMBER 7 L2
    ILOAD 1
    ILOAD 2
    IADD
    ISTORE 3
   L3
    LINENUMBER 8 L3
    GETSTATIC java/lang/System.out : Ljava/io/PrintStream;
    LDC "Hello World :D"
    INVOKEVIRTUAL java/io/PrintStream.println (Ljava/lang/String;)V
   L4
    LINENUMBER 9 L4
    GETSTATIC java/lang/System.out : Ljava/io/PrintStream;
    ILOAD 3
    ICONST_5
    IADD
    INVOKEVIRTUAL java/io/PrintStream.println (I)V
   L5
    LINENUMBER 10 L5
    RETURN
   L6
    LOCALVARIABLE args [Ljava/lang/String; L0 L6 0
    LOCALVARIABLE a I L1 L6 1
    LOCALVARIABLE b I L2 L6 2
    LOCALVARIABLE c I L3 L6 3
    MAXSTACK = 3
    MAXLOCALS = 4
}

```



