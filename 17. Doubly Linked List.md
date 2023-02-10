### A doubly linked list is a data structure that consists of a collection of nodes, where each node has a data field and two pointers. One pointer points to the previous node in the list, and the other pointer points to the next node in the list.

## The Advantages of Doubly Linked List:

### 1.  It allows for easier traversal in both directions
### 2.  It allows for easier insertion and deletion of nodes in the list
### 3.  It is useful for implementing data structures such as stacks and queues, where elements can be inserted or removed from both ends of the list.
## 4. You need not traverse the whole list to find the previous node, as in the case of singly Link List

## The Disadvantages of Doubly Linked List:

### 1.  It requires more memory compared to a singly linked list, as each node requires two pointers instead of one.

### 2.  It requires more time to traverse compared to a singly linked list, as it requires accessing both the next and previous pointers.

### Implementation Of Doubly Linked List:

```java
class Node {
    int data;  // data stored in the node
    Node next; // reference to the next node in the list
    
    // constructor to initialize data and next fields
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class CircularLinkedList {
    Node head; // head node of the linked list

    // constructor to initialize head node
    CircularLinkedList() {
        this.head = null;
    }
    
    // method to insert a new node at the end of the linked list
    public void insert(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            newNode.next = head;
        } else {
            Node temp = head;
            while (temp.next != head) {
                temp = temp.next;
            }
            temp.next = newNode;
            newNode.next = head;
        }
    }
    
    // method to print the linked list
    public void printList() {
        if (head == null) {
            System.out.println("Circular Linked List is empty");
        } else {
            Node temp = head;
            do {
                System.out.print(temp.data + " ");
                temp = temp.next;
            } while (temp != head);
            System.out.println();
        }
    }
}

public class Main {
    public static void main(String[] args) {
        CircularLinkedList list = new CircularLinkedList();
        list.insert(1);
        list.insert(2);
        list.insert(3);
        list.insert(4);
        System.out.println("Circular Linked List: ");
        list.printList();
    }
}

```

## In this code:

### -   The `Node` class defines a single node in the circular linked list, with `data` and `next` fields.
### -   The `CircularLinkedList` class defines the circular linked list as a whole, with a `head` node field.
### -   The `insert` method adds a new node with the given data to the end of the linked list.
### -   The `printList` method prints the elements of the linked list.
### -   The `main` method creates an instance of the `CircularLinkedList` class, inserts elements, and prints the linked list. 