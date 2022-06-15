```java
class Solution
{
    //Function to calculate the span of stockâ€™s price for all n days.
    public static int[] calculateSpan(int price[], int n)
    {
        int[] ans=new int[n];
        
        Stack<Integer> st=new Stack<>();
        st.push(0);
        ans[0]=1;
        
        for(int i=1;i<n;i++){
            while(!st.isEmpty() && price[st.peek()]<=price[i]){
                st.pop();
            }
            
            ans[i]=!st.isEmpty() ? i-st.peek() : i+1;
            st.push(i);
        }
        
        return ans;
    }
    
}
```
