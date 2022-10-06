<h1>Circular Linked List</h1>
<p>The circular linked list is a linked list where all nodes are connected to form a circle. In a circular linked list, the first node and the last node are connected to each other which forms a circle. There is no NULL at the end.</p>

<h2>Circular singly linked list</h2>
<p> The last node of the list contains a pointer to the first node of the list. We traverse the circular singly linked list until we reach the same node where we started. The circular singly linked list has no beginning or end. No null value is present in the next part of any of the nodes.</p>

<h2>Circular Doubly linked list</h2>
<p>Circular Doubly Linked List has properties of both doubly linked list and circular linked list in which two consecutive elements are linked or connected by the previous and next pointer and the last node points to the first node by the next pointer and also the first node points to the last node by the previous pointer.</p>

<h2>PrintList of Circular Linked List</h2>

```java

static void printList(Node head)
{
    Node temp = head;
    
    // If linked list is not empty
    if (head != null) 
    {
        
        // Keep printing nodes till we reach the first node
        // again
        do 
        {
            System.out.print(temp.data + " ");
            temp = temp.next;
        } while (temp != head);
    }
}
```

<h2>Function to insert a node
    at the beginning of a Circular
    linked list</h2>

```java

static Node push(Node head_ref, int data)
    {
        Node ptr1 = new Node();
        Node temp = head_ref;
        ptr1.data = data;
        ptr1.next = head_ref;
  
        /* If linked list is not null
        then set the next of last node */
        if (head_ref != null) {
            while (temp.next != head_ref)
                temp = temp.next;
            temp.next = ptr1;
        }
        else
            ptr1.next = ptr1;
  
        head_ref = ptr1;
  
        return head_ref;
    }
```

<h1>Check if a linked list is Circular Linked List</h1>
 <p>A linked list is called circular if it is not NULL-terminated and all nodes are connected in the form of a cycle. Below is an example of a circular linked list.</p>
 <ul>
 <li>An empty linked list is considered circular.</li>
 <li>The idea is to store head of the linked list and traverse it. If iterator reachs NULL, linked list is not circular. else If it reaches head again, then linked list is circular. </li>
 
 </ul>
    
    
```java
static boolean isCircular(Node head)
    {
        // An empty linked list is circular
        if (head == null)
            return true;
 
        // Next of head
        Node node = head.next;
 
        // This loop would stop in both cases (1) If
        // Circular (2) Not circular
        while (node != null && node != head)
            node = node.next;
 
        // If loop stopped because of circular
        // condition
        return (node == head);
    }    
```    
    
    
  
 
  
    
    


