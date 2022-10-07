<h1>Queue Data Structure</h1>
<p>A queue is defined as a linear data structure that is open at both ends and the operations are performed in First In First Out (FIFO) order.</p>
<p>We define a queue to be a list in which all additions to the list are made at one end, and all deletions from the list are made at the other end.  The element which is first pushed into the order, the operation is first performed on that.</p>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20220816162225/Queue.png">

<h2>Characteristics of Queue:</h2>
<ul>
  <li>Queue can handle multiple data</li>
   <li>We can access both ends.</li>
   <li>They are fast and flexible. </li>
</ul>

<h2>Queue Representation:</h2>
<p>Like stacks, Queues can also be represented in an array: In this representation, the Queue is implemented using the array. Variables used in this case are</p>
<ul>
  <li>Queue: the name of the array storing queue elements.</li>
   <li>Front: the index where the first element is stored in the array representing the queue.</li>
   <li>Rear: the index where the last element is stored in an array representing the queue.</li>
</ul>

<hr>
<h1>Array representation of queue:</h1>

```java
import java.io.*;
class GFG {
   
  // A structure to represent a queue
  static class Queue{
      int front, rear, size;
    int cap;
    int arr[];
  }
   
    // Function to create a queue of given capacity
    // It initializes size of queue as 0
    Queue createQueue(int cap)
    {
        Queue queue = new Queue();
        queue.cap = cap;
        queue.front = 0;
        queue.size = 0;
 
        queue.rear = cap - 1;
        queue.arr = new int[queue.cap];
        return queue;
    }
}
```

<hr>
<h1>Linked List Representation of Queue:</h1>

```java
import java.io.*;
 
class GFG {
   
  static class QNode{
      int data;
    QNode next;
     
    QNode(int data){
        this.data = data;
          next = null;
    }
     
  }
   
  static class Queue{
      QNode front,rear;
    Queue(){
        front = null;
          rear = null;
    }
  }
   
}
```

