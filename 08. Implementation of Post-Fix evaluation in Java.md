``` java
import java.util.Scanner;
import java.util.Stack;
import java.util.StringTokenizer;
public class Post{
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in); 
        // Creating a scanner obejct to take a postfix expr as input from user
        Stack<Integer> Stk = new Stack<Integer>();
        // Creating a new stack using built in java function
        String expr=sc.nextLine();
/** reading the input by using sc object created earlier and storing  it into the expr variable*/
        StringTokenizer s= new StringTokenizer(expr);
/*using the string tokenizer we can split the input expression and store each operand and operator as a string to traverse it later */
        String currentSymbol;
        Pattern p = Pattern.comple("[0-9]+"); 
// it creates a sequence of a pattern that can be matched using matcher method of the pattern class
        Matcher m;
        while(s.hasMoreTokens()) {
/*s.hasMoreTokens checks if there are any string in the input string seperated by spaces that StringTokenizer Split earlier, it is a way to traverse the string and it returns false one string is traversed */
             currentSymbol=s.nextToken();
/*Will return the current string hasMoreTokens is on and store it in currentSymbol variable*/
             m=p.matcher(currentSymbol);
             if(m.matches()) {
/*m.matches returns true if the string in currentSymbol matches any character in the pattern object, if it does it gets pushed into the stack*/             
                 Stk.push(Integer.valueOf(currentSymbol)); // creates an int object and pushes it into the stack Stk
                 }
                 else {
                       // if the current symbol is an operator
                       Integer op2=Stk.pop();
                       Integer op1=Stk.pop();
                       //popping the last two integer objects out of the stack
                       Integer result;
                       switch(currentSymbol){
                       case: "+" : result = op1.intValue()+op2.intValue();
// switch case checks the current symbol, intValue() converts the int object to an int value                   
                       Stk.push(result);
                       break;
                       case: "-" : result = op1.intValue()-op2.intValue();
                       Stk.push(result);
                       break
                       case: "*" : result = op1.intValue()*op2.intValue();
                       Stk.push(result);
                       break
                       case: "/" : result = op1.intValue()/op2.intValue();
                       Stk.push(result);
                       break
                       }
                 
                 }

        }

     System.out.print(Stk.pop().intValue();    
        
    }
}

```