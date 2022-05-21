```java
class Solution {
    public static int checkRedundancy(String s) {
        Stack<Character> st=new Stack<>();
        
        for(char ch: s.toCharArray()){
            if(ch!=')'){
                st.push(ch);
            }else{
                if(st.peek()=='('){
                    return 1;
                }
                int count=0;
                while(!st.isEmpty() && st.peek()!='('){
                    st.pop();
                    count++;
                }
                if(count<2) return 1;
                st.pop();
            }
        }
        
        return 0;
    }
}
    
```
