# Stack

> Last in First out

<ins>Operations</ins>  
1. push  
2. pop
3. peek  
4. size  

Insertion and extraction done at one end only

# Stack structure

![stack](https://user-images.githubusercontent.com/16437905/171616539-beb603b4-4296-4489-9cc4-6344ee7eb713.jpeg)


# When to use stacks

> To keep track of the lastest / last operation made,   
> add to the top and remove from the top  

# Implemenation

can be implemented using   
arrays, dynamic arrays, singly linked list, doubly linked list  

**<ins>Java Default implementation</ins>**    

<ins>Stack</ins>  
> Stack class in java internally use Vector class which is a synchronised dynamic array   
  
Vector is used by Stack class because, Stack and Vector are legacy classes created before Arraylist   

<ins>Deque interface</ins>   

> Java Doc says,  
> 
> A more complete and consistent set of LIFO stack operations is provided by the Deque   
> interface and its implementations, which should be used in preference to Stack class  

<ins>LinkedList class implements Deque</ins>

Deque\<Integer> stack = new LinkedList<>();

<ins>ArrayDeque class implements Deque</ins>

Deque\<Integer> stack = new ArrayDeque<>(); 

# Time Complexity
  
Best implementation is using linked list? check this    

| Operations | Stack implemented using linked list
:---: | :---:
push()         | O(1)
pop()          | O(1)
peek()         | O(1)
size()         | O(1)
  

# Expression Evaluation  
  
<ins>Reverse Polish Notation</ins>     
> Infix to Postfix
  
A + B --> AB+  
3 * 4 --> 34*

7 * 4 + 1 - 3 * 4 --> 74 * 1 + 34 * -   
computer does not know that multiplication(or any operator's precedence) has higher precedence,   
so infix expression is converted to postfix using stack, and the postfix expression is evaluated using stack  

No brackets or parentheses is required in this notation and it is used in RPN calculators  

# Real world applications

1. Undo/Redo
2. Back button
3. Program/Function call stack
4. Compiler bracket checks
5. Expression evaluation (RPN Calculators)
