Given string S representing a postfix expression, the task is to evaluate the expression and find the final value. Operators will only include the basic arithmetic operators like *, /, + and -.

 

Example 1:

Input: S = "231*+9-"
Output: -4
Explanation:
After solving the given expression, 
we have -4 as result.

class Solution
{
    //Function to evaluate a postfix expression.
    public static int evaluatePostFix(String S)
    {
          Stack<Integer> stack = new Stack<>();

        char ch[] = S.toCharArray();

        for(char i : ch)

        {

            if(i >= '0'  && i<= '9' )

            {

                stack.push((int) i - '0');   // if it is -8 '- 0 ' convert it into 8;

            }

            else

            {

                int op2 = stack.pop();

                int op1 = stack.pop();

               switch(i)

               {

                   case '+':

                       stack.push(op1 + op2);

                       break;

                   case '-':

                       stack.push(op1 - op2);

                        break;

                   case '*':

                       stack.push(op1 * op2);

                        break;

                   case '/':

                       stack.push(op1 / op2);

                        break;

               }

            }

        }

        return stack.pop();

    }

}

