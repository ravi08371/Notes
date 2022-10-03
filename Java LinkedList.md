# Notes
All important questions and notes.

<h1>Java LinkedList Imp Ques</h1>

```java
// Online Java Compiler
// Use this editor to write, compile and run your Java code online
import java.util.*;

class LinkedList {
   static Node head;
    
    static class Node{
        int data;
        Node next;
        
        Node(int d){
            this.data = d;
            next = null;
        }
    }
    
    public void push(int new_data){
        Node new_node = new Node(new_data);
        new_node.next = head;
        head = new_node; 
    }
    
    public void printList(){
        Node n = head;
        while(n != null){
            System.out.print(n.data + " ");
            n = n.next;
        }
    }
    void deleteNode(int key){
        Node temp = head,prev = null;
        
        if(temp != null && temp.data == key){
            head = temp.next;
            return;
        }
        
        while(temp != null && temp.data != key){
            prev = temp;
            temp = temp.next;
        }
        
        if(temp == null){
            return;
            
        }
        prev.next = temp.next;
    }
    
    public boolean search(Node head,int x){
        Node current = head;
        
        while(current != null){
            if(current.data == x)
            return true;
            current = current.next;
        }
        return false;
    }
    void deletell(){
        head = null;
    }
    
    public void insertAfter(Node prev_node,int new_data){
        if(prev_node == null){
            System.out.println("Node Can't be empty");
            return;
        }
        
        Node new_node = new Node(new_data);
        new_node.next = prev_node.next;
        prev_node.next = new_node;
    }
    
    public void append(int new_data){
        Node new_node = new Node(new_data);
        
        if(head == null){
            head = new Node(new_data);
            return;
            
        }
        
        new_node.next = null;
        
        Node last = head;
        while(last.next != null)
            last = last.next;
            
            last.next = new_node;
            return;
        
    }
    
    public void removeDublicates(){
        Node curr = head;
        
        while(curr != null){
            Node temp = curr;
            
            while(temp != null && temp.data.equals(curr.data)){
                temp = temp.next;
            }
            
            curr.next = temp;
            curr = curr.next;
        }
    }
    
    static Node reverse(Node head){
        if(head == null || head.next == null)
            return head;
            
            Node rest = reverse(head.next);
            head.next.next = head;
            
            head.next = null;
            
            return rest;
    }
    
    
    
    public static void main(String[] args) {
        // System.out.println("Hello, World!");
        
        LinkedList list = new LinkedList();
        list.push(1);
        list.push(2);
        list.push(3);
        list.push(4);
        list.push(5);
        list.push(6);
        
        // list.printList();
        System.out.println(" ");
        list.deleteNode(4);
        list.printList();
        
        if(list.search(list.head,9)){
             System.out.println("Present in LinkedList");
        }else{
            System.out.println("Not Present in LinkedList");
        }
        
        head = reverse(head);
        list.printList();
        
        list.deletell();
        list.printList();
        
    }
}
```
