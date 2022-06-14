```java
class Solution {

    
    // a: input array
    // n: size of array
    // Function to find equilibrium point in the array.
    public static int equilibriumPoint(long arr[], int n) {
        if(n==1)    return 1;
        long sum=0;
        for(long ele: arr) sum+=ele;
        
        long left=arr[0];
        for(int i=1;i<n-1;i++){
            if(left==sum-left-arr[i]){
                return i+1;
            }
            left+=arr[i];
        }
        
        return -1;
    }
}

```
