## There are many applications of a Stack, some of the main ones are:

## 1. Processing function calls: A function is executed in a program whenever it is called. The function called causes a jump from the current sequence to a new sequence of instructions, a stack is used to keep track of the sequence of instructions in a program, let's understand this with an example. 

```java
int sum(int a, int b){
int x=increment(a);
return x+b;
}


public static void main(String args[]) {
int x=5, y=6,z;
z=sum(x,y);
System.out.print(z)
}

int increment(int y);
{
return y+5;
}

```

## In this program, the first piece of code that will get executed is the code inside the main function, but as soon as we get to the 2nd line which is `z=sum(x,y)` the function call causes a jump of control from the current sequence of instructions to the sum function we declared before the main function, and when the sum function gets executed there's a function inside the sum function called increment, this function call also causes the jump of control from sum function to the increment function. As we can see the last function to get called is the increment function, then sum function, then the main function, therefore to keep track of all of these function calls sequentially we need a stack since the LIFO principle helps us keep track of the function in the order they were called.

### Whenever a function is called, it creates a stack frame (a segment of memory inside the stack), which is stores the parameters & local variables of the called function along with the return address (points to the line of instruction that were to be executed after the function call) 

### This is a pictorial representation of the stack frames that will be created during the execution of the example code written above, the first stack frame will get created as soon as the main method is executed, followed by the sum method and the increment method, which will be the last function call in our example. 

![[Function call in stack.png]]

### As soon as the last function gets executed, the stack frame is deleted and the program moves on to the sum function then on to the main function and after main function's execution, the main function stack function is also deleted and the program is terminated. 



![[function call stack frame 2 2.png]]

# Recursion: 

## Recursion is a function that calls itself, stack is used to keep track of all the recursive function calls in a recursive function so that when the base condition or the termination condition is reached (condition that terminates the recursion) the recursion starts 'unwinding' i.e. the last recursive function that was called, and was stored as a stack frame (which contains the local variables and parameters of that particular function) starts getting executed. Hence, a stack is best suited to keep track of the recursive function calls.

## Here's an example of a recursive function: 

![[Recusrion stack application 1.png]]

## Stack Frame Creation During a Recursion Call:



![[Recursion Stack Usage.png]]

### As soon as the last recursive function, in our case the function returned zero, gets executed, the stack frame that was holding that function's local variables, parameters and return address, gets deleted, and it moves on to the next function until all the functions are called and that stack is empty. We can see that keeping track of the order of the functions being executed during the recursion is a necessary condition for the program to give the correct output. 


# Prefix-Postfix Evaluation: 

## It is easier to calculate prefix or postfix expressions for computers (Expressions where operator come before the operator`[Prefix]` i.e. `2+3 will be written as +23 or 3+5*10` = +3*510 and expression where operator comes after the operand `[Postfix] i.e. 4+5 = 45+ or 9*80+3 = 980*3+ `) when compared to infix expressions (Mathematical expression where operand `[+,-,*, /]` comes in the middle of operators like 2+3 or 5*6 or 99 - 4 etc.) 

## As to the reason why it is simpler to evaluate prefix or postfix expression, compared to infix expression is because in infix expression the order in which to solve an expression is determined by the position of the operator relative to operand and the use of parenthesis i.e. if computer had to solve (2+3) x 10 it has to consider that 2+3 is inside the parenthesis, so it will be solved first as parenthesis () has more precedence than the multiplication operator `x`. Therefore, in the case of more complex operations which has a lot more operands and operators and parenthesis, it will be much more computationally complex task to keep track of everything and solve the expression, hence the need to use prefix or postfix expressions as they simplify the operation by placing the operators before or after the operands making it easier for computer to understand the order of operations. 

## When evaluating a prefix or postfix expressions, the computer as soon as it encounters an operand, it pushes it into the stack and as soon as it comes across an operand it pops the last two operands and applies the operator it encountered to the last two operands and pushes the result back in the stack. Due to the LIFO principle, stack is the perfect data structure to keep track of operands, hence eliminating the need to solve the expression by keeping track of the position of operators in relation to operands and parenthesis. For example, consider this postfix expression 234*+ (2x3+4 `[infix form]`)

### Here's how this expression will be evaluated: 
### 1. First computer encounter operand 2, it gets pushed into the stack, 
### 2. As it encounters 3, it also gets pushed into the stack.
### 3. As it encounters 4, it also gets pusher into the stack. 
### 4. But as soon as it encounters * operator, it pops the last two operants 2&3 and multiplies them and pushes the result 6 into the stack 
### 5. When it encounters 4, it also gets pushed into the stack.
### 6. Lastly when it encounters + operator, it once again pops the last two numbers which were 4 & 6 respectively and adds them, resulting in the number 10, which is what we get when we solve the infix form of expression i.e. (2x3)+4 

