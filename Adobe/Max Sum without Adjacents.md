```java
class Solution {
    int findMaxSum(int arr[], int n) {
        int inc=arr[0];
        int exc=0;
        
        for(int i=1;i<n;i++){
            int nexc=Math.max(inc,exc);
            int ninc=arr[i]+exc;
            
            inc=ninc;
            exc=nexc;
        }
        
        return Math.max(inc,exc);
    }
}
```
