```java
class Solution
{
    //Function to find the next greater element for each element of the array.
    public static long[] nextLargerElement(long[] arr, int n)
    { 
        long[] ans=new long[n];
        Arrays.fill(ans,-1L);
        
        Stack<Integer> st=new Stack<>();
        for(int i=0;i<n;i++){
            while(!st.isEmpty() && arr[st.peek()]<arr[i]){
                ans[st.pop()]=arr[i];
            }
            
            st.push(i);
        }
        
        return ans;
    } 
}
```
