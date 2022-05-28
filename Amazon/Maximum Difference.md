```java
class Solution{
    int findMaxDiff(int a[], int n){
        int LS[]=new int[n];
        int RS[]=new int[n];
        
        Stack<Integer> st=new Stack<>();
        for(int i=0;i<n;i++){
            while(!st.isEmpty() && a[st.peek()]>=a[i]){
                st.pop();
            }
            
            if(!st.isEmpty())   LS[i]=a[st.peek()];
            st.push(i);
        }
        
        st.clear();
        for(int i=n-1;i>=0;i--){
            while(!st.isEmpty() && a[st.peek()]>=a[i]){
                st.pop();
            }
            
            if(!st.isEmpty())   RS[i]=a[st.peek()];
            st.push(i);
        }
        
        int ans=0;
        for(int i=0;i<n;i++){
            ans=Math.max(ans,Math.abs(LS[i]-RS[i]));
        }
        
        return ans;
    }
}
```
