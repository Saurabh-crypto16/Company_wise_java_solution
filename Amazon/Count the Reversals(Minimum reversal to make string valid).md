```java
/*
calculate the total number of { and } that make invalid part
eg: "}{{}}{{{" so invalid part is "}{{{"
if total number of invalid part is odd then no answer possible
else answer will be (open+1)/2+(close+1)/2
*/
class Sol
{
    int countRev (String s)
    {
        Stack<Character> st=new Stack<>();
		int open=0,close=0;
		
        for(char c: s.toCharArray()){
            if(c=='{')  st.push(c);
            else {
                if(st.isEmpty())    close++;
                else	st.pop();
            }
        }
        
        open=st.size();
        
        if((open+close)%2!=0)   return -1;
        return (open+1)/2+(close+1)/2;
    }
}
```
