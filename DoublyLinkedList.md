<h1>Doubly Linked List</h1>
<p>A Doubly Linked List (DLL) contains an extra pointer, typically called the previous pointer, together with the next pointer and data which are there in the singly linked list.</p>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL1.png" alt="">


<h2>Decleration</h2>

```java
public class DLL {
     
    // Head of list
    Node head;
 
    // Doubly Linked list Node
    class Node {
        int data;
        Node prev;
        Node next;
 
        // Constructor to create a new node
        // next and prev is by default initialized as null
        Node(int d) 
        { data = d; }
    }
}
```

<h2>Advantages of DLL over the singly linked list</h2>
<ul>
  <li>A DLL can be traversed in both forward and backward directions.</li>
  <li>The delete operation in DLL is more efficient if a pointer to the node to be deleted is given.</li>
  <li>We can quickly insert a new node before a given node.</li>
  <li>In a singly linked list, to delete a node, a pointer to the previous node is needed. To get this previous node, sometimes the list is traversed. In DLL, we can get the previous node using the previous pointer.</li>
</ul>

<h1>Add Node At the front of the DLL</h1>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL_add_front1.png" alt="">

```java
public void push(int new_data)
{
    /* 1. allocate node
     * 2. put in the data */
    Node new_Node = new Node(new_data);
 
    /* 3. Make next of new node as head and previous as NULL
     */
    new_Node.next = head;
    new_Node.prev = null;
 
    /* 4. change prev of head node to new node */
    if (head != null)
        head.prev = new_Node;
 
    /* 5. move the head to point to the new node */
    head = new_Node;
}
```

<h1>Add a node after a given node</h1>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL_add_middle1.png">

```java
public void InsertAfter(Node prev_Node, int new_data)
{
 
    /*1. check if the given prev_node is NULL */
    if (prev_Node == null) {
        System.out.println(
            "The given previous node cannot be NULL ");
        return;
    }
 
    /* 2. allocate node
     * 3. put in the data */
    Node new_node = new Node(new_data);
 
    /* 4. Make next of new node as next of prev_node */
    new_node.next = prev_Node.next;
 
    /* 5. Make the next of prev_node as new_node */
    prev_Node.next = new_node;
 
    /* 6. Make prev_node as previous of new_node */
    new_node.prev = prev_Node;
 
    /* 7. Change previous of new_node's next node */
    if (new_node.next != null)
        new_node.next.prev = new_node;
}
```

<h1>Add a node at the end</h1>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL_add_end1.png">

```java
void append(int new_data)
{
    /* 1. allocate node
     * 2. put in the data */
    Node new_node = new Node(new_data);
 
    Node last = head; /* used in step 5*/
 
    /* 3. This new node is going to be the last node, so
     * make next of it as NULL*/
    new_node.next = null;
 
    /* 4. If the Linked List is empty, then make the new
     * node as head */
    if (head == null) {
        new_node.prev = null;
        head = new_node;
        return;
    }
 
    /* 5. Else traverse till the last node */
    while (last.next != null)
        last = last.next;
 
    /* 6. Change the next of last node */
    last.next = new_node;
 
    /* 7. Make last node as previous of new node */
    new_node.prev = last;
}
```


<h1>Delete Node in Dounly Linked List</h1>

```java
void deleteNode(Node del)
    {
 
        // Base case
        if (head == null || del == null) {
            return;
        }
 
        // If node to be deleted is head node
        if (head == del) {
            head = del.next;
        }
 
        // Change next only if node to be deleted
        // is NOT the last node
        if (del.next != null) {
            del.next.prev = del.prev;
        }
 
        // Change prev only if node to be deleted
        // is NOT the first node
        if (del.prev != null) {
            del.prev.next = del.next;
        }
 
        // Finally, free the memory occupied by del
        return;
    }
```

<h1>Reverse A Doubly Linked List</h1>

```java
void reverse()
    {
        Node temp = null;
        Node current = head;
 
        /* swap next and prev for all nodes of
         doubly linked list */
        while (current != null) {
            temp = current.prev;
            current.prev = current.next;
            current.next = temp;
            current = current.prev;
        }
 
        /* Before changing head, check for the cases like
         empty list and list with only one node */
        if (temp != null) {
            head = temp.prev;
        }
    }
```








