```java
class Solution
{
    //Function to evaluate a postfix expression.
    public static int evaluatePostFix(String S)
    {
        Stack<Integer> st=new Stack<>();
        
        for(char c: S.toCharArray()){
            if(c!='+' && c!='-' && c!='*' && c!='/')    st.push(Integer.parseInt(c+""));
            else{
                int op1=st.pop();
                int op2=st.pop();
                if(c=='+'){
                    st.push(op1+op2);
                }else if(c=='-'){
                    st.push(op2-op1);
                }else if(c=='*'){
                    st.push(op1*op2);
                }else if(c=='/'){
                    st.push(op2/op1);
                }
            }
        }
        
        return st.pop();
    }
}
```
