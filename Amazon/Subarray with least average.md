```java
class Solution{
    public int least_average(int[] arr, int k){
        int n=arr.length;
        if (n < k) return -1;
        
        int res_index = 0,curr_sum = 0;
        for (int i = 0; i < k; i++) curr_sum += arr[i];
        int min_sum = curr_sum;
     
        // Traverse from (k+1)'th element to n'th element
        for (int i = k; i < n; i++) {
            // Add current item and remove first item of
            // previous subarray
            curr_sum += arr[i] - arr[i - k];
     
            // Update result if needed
            if (curr_sum < min_sum) {
                min_sum = curr_sum;
                res_index = (i - k + 1);
            }
        }
        
        return res_index+1;
    }
}
```
