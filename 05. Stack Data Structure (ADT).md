
## Stack is an ordered list of elements which follows 'LIFO' : Last In First Out, which is essentially a method of organizing and manipulating the data structure, it implies that data elements can only be added and removed in LIFO order i.e. Whatever data was added to the stack last will get processed first (added, removed, read) and the data that was added to it first will get processed last. Note: When a new element is added to the stack, it is added to the top of the stack, pushing any previously added elements down. This ensures that the last element added is always at the top of the stack, ready to be removed first if a pop (removing an element) operation is performed. This principle allows for a more efficient manipulation of data in variety of situations like undo & redo operations, parsing expressions, function calls etc.

## The main operations that performed on the stack are:

### 1. Push: Adding data to the top of the stack

### 2. POP: Removing Data from the top of the stack.

### 3. Peek/TOP: This operation reads the element that is at the top of the stack 

### 4. isEmpty: This operation returns a boolean, i.e. True if the stack is empty and False if the stack is not empty.

### 5. Size: This operation returns the size of the stack.

## Implementation of stack: 

```java
class MyStack{
int stk[];
int top;
int size;
Mystack(int s){ //This is a function for declaring a stack with int s as an argument that let's the user enter the size of the stack while calling this function
stk = new int[s]; // Creating a an arrray of size s(argument to be passed by user in place of s when they call this function)
size=s; // Initializing the size varaiable with the argument 's' passed by user
top=-1 //Initializing top variable that will keep track of the stack we created, it will also be used while pushing data into the stack, by being passed later inside the push function we will create as a index value for the array stk
}
}
void push(int item) // int item is an argument that will be passed by the user of the function, used for pushing the data that is passed being here into the stack we created
if(top==size-1){
// This line checks weather the stack is full or not i.e. each time we pass an element we increment top, suppose we have 5 numbers to pass into the stack, {1,2,3,4,5} when we pass 5 in the argument of push function, we increment top variable from -1 to 0 while inserting data in the stack array, and as we pass remaining numbers we keep incrementing the numbers, if we initialized a stack of 5 numbers by the time we pushed all 5 numbers top variable will be incremented from -1 to 4, and if the number is 4 in our case and when we compare it with size-1, it means the stack is full hence we will now return "stack full" or "stack overflowing" as a message to notify the user of this function, if not we simply push the number into the array with an else statement and increment top variable to keep track.
System.out.println("Stack overflowing"};
} else {
stk[++top] = item; // note that we are using prefix increment operator and not postfix i.e. top++ as we initialized top with -1 in Mystack function and since we want the first index passed in the stk array. as the user pushes the first element in the array, to be 0 and not -1, therefore if we used top++ it would've been processed as -1 index and not 0.
}				   
int pop(){
if(top==-1){
Systemp.out.print("Stack Empty");
return -1;
} else{
return stk[top--];
}
}
int peek(){
if(top==-1){
System.out.print("Stack is empty");
return -1;
else {
return stk[top];
}
}
}

boolean isEmpty(){
return top == -1; // This function will return True if top == -1 and false if not
}
boolean isFull(){
return top == size-1; // This function will return True if top == size-1 as top tracks the size of the stack array and if lets say the size of the stack is 5 and we already know that everytime we pushed a number in the array we incremented top variable by 1 which we initialized with -1 at the beginning, therefore, when the array is full top will be incremented to the number equivalent to size-1, since we are starting with -1 i.e. 4 hence top == -1 will return True. 
}

```