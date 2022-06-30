```java
class Solution {
    // Function to find maximum product subarray
    long maxProduct(int[] arr, int n) {
        if(n==0)    return 0L;
        
        long min=arr[0],max=arr[0],result=arr[0];
        for(int i=1;i<n;i++){
            long temp_max=Math.max(arr[i]*max,Math.max(arr[i]*min,arr[i]));
            min=Math.min(arr[i]*max,Math.min(arr[i]*min,arr[i]));
            
            max=temp_max;
            result=Math.max(result,max);
        }
        
        return result;
    }
}
```
