## A linked list is a linear data structure where each element is a separate object known as a node. It consists of the following components:

### 1. Head: It is a reference to the first node in the linked list. It is null if the list is empty.

### 2.  Node: Each node contains two fields: data and next. The data field stores the information or element in the node. The next field is a reference to the next node in the list. The last node in the list will have the next field set to null.

### 3. Data: It is the information stored in the node. It can be any data type like integer, string, etc.

### 4. Next: It is a reference to the next node in the linked list. It points to null for the last node in the list.

### 5. Tail: It is a reference to the last node in the linked list. It is used to append elements to the end of the list efficiently.

## Together, these components allow linked lists to store data and traverse through the elements easily.

### In linked lists, the term "null" is used to refer to a special value that indicates the end of the list. Each node in a linked list contains a data element and a reference (also called a "pointer") to the next node in the list. The last node in the list is typically set to have a reference to "null," indicating that there are no more nodes in the list. In this way, "null" acts as a sentinel value and allows algorithms that traverse the linked list to know when they have reached the end of the list.

### A pictorial representation of a linked list:

![[Linkedlist.png]]

## Main operations that can be performed on the Linked List are:

### 1.  Insertion: Adding an element to the linked list
### 2.  Deletion: Removing an element from the linked list
### 3.  Searching: Finding an element in the linked list
### 4.  Traversal: Visiting each node of the linked list

## Properties of a Linked List:

### 1.  Dynamic Size: Linked lists can grow or shrink dynamically, allocating or freeing memory as required.
    
### 2.  Linear Structure: Linked lists are linear in structure, meaning that data elements are stored one after the other in a specific order.
    
### 3.  Dynamic Allocation of Memory: Each node in a linked list is separately allocated in memory and connected to each other, rather than being stored in a single block of memory as in arrays.
    
### 4.  Ease of Insertion and Deletion: Linked lists offer ease of insertion and deletion of elements, as it only requires adjusting the pointers of the adjacent nodes.
    
### 5.  No Memory Waste: Linked lists do not waste memory as arrays do, as memory is only allocated for the actual number of elements in the list.
    
### 6.  Limited Random Access: Linked lists do not allow for random access because the elements of a linked list are stored in a non-contiguous manner in memory. Unlike arrays, where the elements are stored in a contiguous block of memory and can be accessed in constant time using an index, in linked list each element is stored in a separate memory block and can only be accessed by iterating through the list from the beginning to the desired element. This makes accessing an element at a specific index in a linked list a linear time operation, as opposed to a constant time operation for arrays.
    
### 7.  Flexible Size: Linked lists can grow in size dynamically, as new elements can be added to the list, even after its creation.
    
### 8.  Costly Element Access: Element access in linked lists is slower than arrays, as it requires traversing the list to reach the desired element.

## Inbuilt Java Linked List Library:

### In Java, you can use the `java.util.LinkedList` class to create a linked list. The following is a simple example to create a linked list:

```java
import java.util.LinkedList;

public class Example {
  public static void main(String[] args) {
    LinkedList<Integer> linkedList = new LinkedList<>();

    // Adding elements to the linked list
    linkedList.add(1);
    linkedList.add(2);
    linkedList.add(3);

    System.out.println("Linked List: " + linkedList);
  }
}
```

### Some of the commonly used methods of the LinkedList class are:

#### 1.  `add(element)`: Adds an element to the end of the linked list.

#### 2.  `addFirst(element)`: Adds an element to the beginning of the linked list.

#### 3.  `addLast(element)`: Adds an element to the end of the linked list.

#### 4.  `get(index)`: Returns the element at the specified position in the linked list.

#### 5.  `remove(element)`: Removes the first occurrence of the specified element from the linked list.

#### 6.  `removeFirst()`: Removes and returns the first element from the linked list.

#### 7.  `removeLast()`: Removes and returns the last element from the linked list.

#### 8.  `set(index, element)`: Replaces the element at the specified position in the linked list with the specified element.

#### 9.  `size()`: Returns the number of elements in the linked list.

#### 10.  `contains(element)`: Returns true if the linked list contains the specified element. 

## Linked lists have several applications, including:

### 1.  Dynamic memory allocation: Linked lists can be used to implement dynamic memory allocation, where memory is assigned to the data elements as and when required.
    
### 2.  Implementing Stacks and Queues: Linked lists can be used to implement data structures like Stacks and Queues, where elements are added and removed from the end or front of the list.
    
### 3.  Implementing Associative Arrays: Linked lists can be used to implement associative arrays where elements are stored as key-value pairs.
    
### 4.  Implementing Graphs and Trees: Linked lists can be used to implement graph and tree data structures.
    
### 5.  Managing Cache Memory: Linked lists can be used to manage cache memory, where the least recently used data elements can be removed from the list to make space for new data elements.
    
### 6.  Maintaining Database Records: Linked lists can be used to maintain database records, where data elements can be added, deleted, or updated in an efficient manner.
    
### 7.  Multi-threading: Linked lists can be used to implement multi-threading, where data elements are shared between multiple threads.