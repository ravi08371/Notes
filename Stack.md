<h1>Stack Data Structure</h1>
<p>Stack is a linear data structure which follows a particular order in which the operations are performed. The order may be LIFO(Last In First Out) or FILO(First In Last Out).</p>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2013/03/stack.png">

<p>There are many real-life examples of a stack. Consider an example of plates stacked over one another in the canteen. The plate which is at the top is the first one to be removed, i.e. the plate which has been placed at the bottommost position remains in the stack for the longest period of time. So, it can be simply seen to follow LIFO(Last In First Out)/FILO(First In Last Out) order.</p>

<h2>Basic Operations on Stack</h2>
<ul>
  <li>push() to insert an element into the stack</li>
  <li>pop() to remove an element from the stack</li>
  <li>top() Returns the top element of the stack.</li>
  <li>isEmpty() returns true is stack is empty else false</li>
  <li>size() returns the size of stack</li>
</ul>

<h3>Types of Stack</h3>
<ul>
  <li><strong>Register Stack:</strong>This type of stack is also a memory element present in the memory unit and can handle a small amount of data only. The height of the register stack is always limited as the size of the register stack is very small compared to the memory.</li>
  <li><strong>Memory Stack:</strong>This type of stack can handle a large amount of memory data. The height of the memory stack is flexible as it occupies a large amount of memory data.</li>
</ul>

<h3>Applications of Stack</h3>
<ul>
  <li>Redo-undo features at many places like editors, photoshop.</li>
  <li>Forward and backward features in web browsers</li>
  <li>Used in many algorithms like Tower of Hanoi, tree traversals, stock span problems, and histogram problems.</li>
  <li>In Memory management, any modern computer uses a stack as the primary management for a running purpose. Each program that is running in a computer system has its own memory allocations</li>
  
</ul>

<h1>Implementation of Stack</h1>
<h4>Using Array</h4>

```java
class Stack {
    static final int MAX = 1000;
    int top;
    int a[] = new int[MAX]; // Maximum size of Stack
  
    boolean isEmpty()
    {
        return (top < 0);
    }
    Stack()
    {
        top = -1;
    }
  
    boolean push(int x)
    {
        if (top >= (MAX - 1)) {
            System.out.println("Stack Overflow");
            return false;
        }
        else {
            a[++top] = x;
            System.out.println(x + " pushed into stack");
            return true;
        }
    }
  
    int pop()
    {
        if (top < 0) {
            System.out.println("Stack Underflow");
            return 0;
        }
        else {
            int x = a[top--];
            return x;
        }
    }
  
    int peek()
    {
        if (top < 0) {
            System.out.println("Stack Underflow");
            return 0;
        }
        else {
            int x = a[top];
            return x;
        }
    }
     
    void print(){
    for(int i = top;i>-1;i--){
      System.out.print(" "+ a[i]);
    }
  }
}
  
// Driver code
class Main {
    public static void main(String args[])
    {
        Stack s = new Stack();
        s.push(10);
        s.push(20);
        s.push(30);
        System.out.println(s.pop() + " Popped from stack");
        System.out.println("Top element is :" + s.peek());
        System.out.print("Elements present in stack :");
        s.print();
    }
}
//Output
Output
10 pushed into stack
20 pushed into stack
30 pushed into stack
30 Popped from stack
Top element is : 20
Elements present in stack : 20 10 
```

<h4>Disadvantages of array implementation:</h4>
<p>It is not dynamic and It doesn't grow and shrink depending on needs at runtime</p>
<h4>Advantages of array implementation</h4>
<p>Easy to implement</p>
<p>Memory is saved as pointers are not involved</p>

<h3>Implementing Stack using Linked List:</h3>

```java
public class StackAsLinkedList {
  
    StackNode root;
  
    static class StackNode {
        int data;
        StackNode next;
  
        StackNode(int data) { this.data = data; }
    }
  
    public boolean isEmpty()
    {
        if (root == null) {
            return true;
        }
        else
            return false;
    }
  
    public void push(int data)
    {
        StackNode newNode = new StackNode(data);
  
        if (root == null) {
            root = newNode;
        }
        else {
            StackNode temp = root;
            root = newNode;
            newNode.next = temp;
        }
        System.out.println(data + " pushed to stack");
    }
  
    public int pop()
    {
        int popped = Integer.MIN_VALUE;
        if (root == null) {
            System.out.println("Stack is Empty");
        }
        else {
            popped = root.data;
            root = root.next;
        }
        return popped;
    }
  
    public int peek()
    {
        if (root == null) {
            System.out.println("Stack is empty");
            return Integer.MIN_VALUE;
        }
        else {
            return root.data;
        }
    }
  
    // Driver code
    public static void main(String[] args)
    {
  
        StackAsLinkedList sll = new StackAsLinkedList();
  
        sll.push(10);
        sll.push(20);
        sll.push(30);
  
        System.out.println(sll.pop()
                           + " popped from stack");
  
        System.out.println("Top element is " + sll.peek());
    }
}
//output
10 pushed to stack
20 pushed to stack
30 pushed to stack
30 popped from stack
Top element is 20
Elements present in stack : 20 10 
```

<h4>Advantages of Linked List implementation</h4>
<p>The linked list implementation of a stack can grow and shrink according to the needs at runtime</p>
<p>It is used in many virtual machines like JVM.</p>
<p>Stacks are more secure and reliable as they do not get corrupted easily.</p>
<p>Stack cleans up the objects automatically.</p>

<h4>Disadvantages of Linked List implementation</h4>
<p>*Requires extra memory due to the involvement of pointers.</p>
<p>*Random accessing is not possible in stack.</p>
<p>*The total size of the stack must be defined before.</p>
<p>*If the stack falls outside the memory it can lead to abnormal termination.</p>

<h1>How to create a Stack</h1>

```java
import java.io.*;
import java.util.*;
  
class Test
{   
    // Pushing element on the top of the stack
    static void stack_push(Stack<Integer> stack)
    {
        for(int i = 0; i < 5; i++)
        {
            stack.push(i);
        }
    }
      
    // Popping element from the top of the stack
    static void stack_pop(Stack<Integer> stack)
    {
        System.out.println("Pop Operation:");
  
        for(int i = 0; i < 5; i++)
        {
            Integer y = (Integer) stack.pop();
            System.out.println(y);
        }
    }
  
    // Displaying element on the top of the stack
    static void stack_peek(Stack<Integer> stack)
    {
        Integer element = (Integer) stack.peek();
        System.out.println("Element on stack top: " + element);
    }
      
    // Searching element in the stack
    static void stack_search(Stack<Integer> stack, int element)
    {
        Integer pos = (Integer) stack.search(element);
  
        if(pos == -1)
            System.out.println("Element not found");
        else
            System.out.println("Element is found at position: " + pos);
    }
  
  
    public static void main (String[] args)
    {
        Stack<Integer> stack = new Stack<Integer>();
  
        stack_push(stack);
        stack_pop(stack);
        stack_push(stack);
        stack_peek(stack);
        stack_search(stack, 2);
        stack_search(stack, 6);
    }
}
```

```java
import java.util.*;
import java.io.*;
  
public class StackDemo {
  
      // Main Method
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<String> stack = new Stack<String>();
  
        // Use push() to add elements into the Stack
        stack.push("Welcome");
        stack.push("To");
        stack.push("Geeks");
        stack.push("For");
        stack.push("Geeks");
  
        // Displaying the Stack
        System.out.println("Initial Stack: " + stack);
  
        // Fetching the element at the head of the Stack
        System.out.println("The element at the top of the"
                           + " stack is: " + stack.peek());
  
        // Displaying the Stack after the Operation
        System.out.println("Final Stack: " + stack);
    }
}
```

<hr><hr>
<h1>How to Reverse a Stack using Recursion</h1>

```java
import java.util.Stack;
 
class Test {
 
    // using Stack class for
    // stack implementation
    static Stack<Character> st = new Stack<>();
 
    /
    static void insert_at_bottom(char x)
    {
 
        if (st.isEmpty()){
            st.push(x);
        } else {
            char a = st.peek();
            st.pop();
            insert_at_bottom(x);

            st.push(a);
        }
    }
 
    // Below is the function that
    // reverses the given stack using
    // insert_at_bottom()
    static void reverse()
    {
        if (st.size() > 0) {
 
          
            char x = st.peek();
            st.pop();
            reverse();
 
            insert_at_bottom(x);
        }
    }
 
    // Driver Code
    public static void main(String[] args)
    {
 
        // push elements into
        // the stack
        st.push('1');
        st.push('2');
        st.push('3');
        st.push('4');
 
        System.out.println("Original Stack");
 
        System.out.println(st);
 
        // function to reverse
        // the stack
        reverse();
 
        System.out.println("Reversed Stack");
 
        System.out.println(st);
    }
}
```

<h1>Sort a Stack Using a Temporary Stack</h1>

```java
import java.util.*;
 
class SortStack
{
    // This function return the sorted stack
    public static Stack<Integer> sortstack(Stack<Integer>
                                             input)
    {
        Stack<Integer> tmpStack = new Stack<Integer>();
        while(!input.isEmpty())
        {
            // pop out the first element
            int tmp = input.pop();
         
            // while temporary stack is not empty and
            // top of stack is greater than temp
            while(!tmpStack.isEmpty() && tmpStack.peek()
                                                 > tmp)
            {
                // pop from temporary stack and
                // push it to the input stack
            input.push(tmpStack.pop());
            }
             
            // push temp in temporary of stack
            tmpStack.push(tmp);
        }
        return tmpStack;
    }
     
    // Driver Code
    public static void main(String args[])
    {
        Stack<Integer> input = new Stack<Integer>();
        input.add(34);
        input.add(3);
        input.add(31);
        input.add(98);
        input.add(92);
        input.add(23);
     
        // This is the temporary stack
        Stack<Integer> tmpStack=sortstack(input);
        System.out.println("Sorted numbers are:");
     
        while (!tmpStack.empty())
        {
            System.out.print(tmpStack.pop()+" ");
        }
    }
}
```






