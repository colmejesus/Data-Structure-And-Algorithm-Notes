```java
public class myQueue {
   int queue[] 
   int capacity;
   int front;
   int rear;

public myQueue(int size)
{
front=rear=0;
capacity=size;
queue = new queue[capacity];
}

   public void enQueue(int data)
   {
      if(capacity==rear)
       {
        System.out.println("Queue is full");
// since rear gets incremented everytime data is inserted in the queue if capacity of the queue that we initiated queueIntialization function, is equal to the rear that means queue is full 
        }
        else {
            queue[rear]=int data;
// if the queue is not full we insert the data item in the array at the rear and increment the rear pointer to have a refence to the pointer in case we need to delete any item.   
             rear++;
             }
   
   
   }
 public void deQueue()
 {
    if(front==rear)
    {
      System.out.print("Queue is empty");
    }
    else {
      for(i=0;i<rear-1;i++){
         queue[i] = queue[i+1];
      } rear--;
    }
 
 }
public void dislay()
{
   if(front==rear)
   { 
      System.out.print("Queue is empty");
      
   }
   else
   {
     for(i=front;i<rear-1;i++);
     System.out.print(queue[i]);
   }
}
public static void main(String args[])
{
  myQueue queue = new myQueue(5);
  queue.enqueue(1);
  queue.enqueue(4);
  queue.dequeue();
  
  
}
}
```