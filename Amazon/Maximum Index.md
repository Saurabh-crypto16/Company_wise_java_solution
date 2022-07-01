```java
class Solution{
    
    // A[]: input array
    // N: size of array
    // Function to find the maximum index difference.
    static int maxIndexDiff(int arr[], int n) {
        int lmin[]=new int[n];
        int rmax[]=new int[n];
        
        lmin[0]=arr[0];
        for(int i=1;i<n;i++)    lmin[i]=Math.min(arr[i],lmin[i-1]);
        
        rmax[n-1]=arr[n-1];
        for(int i=n-2;i>=0;i--)    rmax[i]=Math.max(arr[i],rmax[i+1]);
        
        int maxDiff=0;
        int j=0,i=0;
        while(i<n && j<n){
            if(lmin[i]<=rmax[j]){
                maxDiff=Math.max(maxDiff,j-i);
                j++;
            }else{
                i++;
            }
        }
        
        return maxDiff;
    }
}
```
