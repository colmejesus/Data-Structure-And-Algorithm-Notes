```java
import java.util.Stack;
import java.util.StringTokenizer;
public class Parenthesis {
    public static boolean balancedExpr(String expr) {
    Stack<String> Stk = new Stack<String>();
    // stack for storing the parenthesis
    StringTokenizer s = new StringTokenizer(expr);
    // used for traversing through the expression given as an argument
    String currentSymbol;
    String stacksymb;
    boolean valid=true;
    while(s.hasMoreTokens()) {
        currentSymbol=s.nextToken();
        //holds the symbol
        switch(currentSymbol) {
        case "(":
        case "{":
        case "[": Stk.push(currentSymbol);
                   break;
        case ")" if(Stk.empty()) {valid=flase; break;}
                 else{
                 stacksymb=Stk.pop();
                 if(!(stacksymb.equals("("))) {valid=flase; break;}
                 }
        case "}" if(Stk.empty()) {valid=flase; break;}
                 else{
                 stacksymb=Stk.pop();
                 if(!(stacksymb.equals("("))) {valid=flase; break;}
                 }
         case ")" if(Stk.empty()) {valid=flase; break;}
                 else{
                 stacksymb=Stk.pop();
                 if(!(stacksymb.equals("("))) {valid=flase; break;}
                 }
                 break;
                 default: break;        
        }
        
    }
       if(!valid)return false;
    }
    if(!(Stk.isEmpty()))return false;

return true;
}

public static void main(String[] args) {
    System.out.println(balancedExpr("{ ( ) }"));
}

```