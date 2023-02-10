## A queue is a linear data structure that follows the First-In-First-Out (FIFO) principle, meaning that the first element to be inserted into the queue will be the first one to be removed. Hence, data items can only be deleted from the front end of the queue, and they can only be inserted at the rear end of the queue.

## Queue is an Abstract Data Type (ADT) that has the following operations:

### 1.  enqueue: This operation adds an element to the end of the queue.
    
### 2.  dequeue: This operation removes an element from the front of the queue.
    
### 3.  peek: This operation returns the element at the front of the queue without removing it.
    
### 4.  isEmpty: This operation checks if the queue is empty or not.
    
### 5.  size: This operation returns the number of elements in the queue.

## These operations form the basic functionality of a queue. Depending on the implementation, a queue may also have additional operations like clearing the queue, finding the index of an element, and so on. The specific operations provided by a queue implementation will depend on the requirements of the particular application.

## Here are some other properties of a queue:

### 1. Capacity: The maximum number of elements that can be stored in the queue. If a queue has a fixed capacity, attempting to add an element to a full queue will result in an error.

### 2. Size: The number of elements currently stored in the queue.

### 3. Front: The front of the queue is the first element to be removed.

### 4. Rear: The rear of the queue is the position where new elements are inserted.

### Queues are commonly used in computer science for tasks such as scheduling processes, handling events, and implementing algorithms.

## There are many real-life applications of queues, including:

### 1.  Task scheduling: In computer systems, tasks are often scheduled and executed in the order they are received. A queue is used to store and manage the tasks, with the oldest task being executed first.
    
### 2.  Call center management: In a call center, incoming calls are handled in the order they are received. A queue is used to store the calls and ensure that they are handled in the correct order.
    
### 3.  Printing: Printers use a queue to store the print jobs that are sent to them. Jobs are printed in the order they are received, and the queue ensures that multiple jobs are handled correctly.
    
### 4.  Banking: Banks use queues to manage customer transactions. Customers are served in the order they arrived, and a queue ensures that each customer is served fairly and in the correct order.
    
### 5.  Transportation: Airports, bus stations, and train stations use queues to manage passenger boarding. Passengers are boarded in the order they arrived, and a queue ensures that boarding is managed efficiently and fairly.
    
### 6.  Resource allocation: In computer systems, resources such as memory, disk space, and network bandwidth are allocated using queues. Requests for resources are added to the queue, and the first request is fulfilled first.
    
### 7.  Web server requests: Web servers use queues to manage incoming requests. Requests are added to the queue, and the server processes each request in the order it was received.
