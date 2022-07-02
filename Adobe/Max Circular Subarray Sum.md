```java
class Solution{

    // a: input array
    // n: size of array
    //Function to find maximum circular subarray sum.
    
    /*
    Answer will be either max continous sum or circular continous sum
    
    To max max continous sum use kadanes
    
    To get max circular sum, change sign of each element in array and find the max 
    continous sum using kadanes and the negative of that sum will miimum continous sum
    subarray and subtract it from overall sum to get the max circular sum subarray
    */
    static int circularSubarraySum(int a[], int n) {
        int x=kadane(a,n);
        
        int y=0;
        for(int i=0;i<n;i++){
            y+=a[i];
            a[i]*=-1;
        }
        
        int z=kadane(a,n);
        
        if(y+z==0)  return x;
        return Math.max(x,y+z);
    }
    static int kadane(int a[], int n) {
        int csum=a[0],msum=a[0];
        
        for(int i=1;i<n;i++){
            csum+=a[i];
            if(csum<a[i])   csum=a[i];
            
            msum=Math.max(csum,msum);
        }
        
        return msum;
    }
}
```
