```java
class CircularQueue {
  private int[] queue;
  private int front;
  private int rear;
  private int size;
  private int capacity;

  // constructor to initialize the values
  public CircularQueue(int capacity) {
    // store the capacity
    this.capacity = capacity;
    // initialize the queue with the given capacity
    queue = new int[capacity];
    // initialize the front and rear to -1 as the queue is empty
    front = -1;
    rear = -1;
    // initialize size to 0 as the queue is empty
    size = 0;
  }

  // function to check if the queue is full
  public boolean isFull() {
    // the queue is full if the size is equal to the capacity
    return (size == capacity);
  }

  // function to check if the queue is empty
  public boolean isEmpty() {
    // the queue is empty if the size is 0
    return (size == 0);
  }

  // function to enqueue an element into the queue
  public void enqueue(int element) {
    // check if the queue is full
    if (isFull()) {
      // if the queue is full, print the message and return
      System.out.println("Queue is full, cannot enqueue element");
      return;
    }
    // calculate the new rear index
    rear = (rear + 1) % capacity;
    // enqueue the element into the rear index
    queue[rear] = element;
    // increment the size
    size++;
    // if front is -1, set it to the rear as this is the first element in the queue
    if (front == -1) {
      front = rear;
    }
  }

  // function to dequeue an element from the queue
  public int dequeue() {
    // check if the queue is empty
    if (isEmpty()) {
      // if the queue is empty, print the message and return Integer.MIN_VALUE
      System.out.println("Queue is empty, cannot dequeue element");
      return Integer.MIN_VALUE;
    }
    // store the element from the front
    int element = queue[front];
    // calculate the new front index
    front = (front + 1) % capacity;
    // decrement the size
    size--;
    // if size is 0, reset the front and rear to -1
    if (size == 0) {
      front = -1;
      rear = -1;
    }
    // return the dequeued element
    return element;
  }
}


```