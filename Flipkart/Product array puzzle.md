```java
class Solution 
{ 
	public static long[] productExceptSelf(int nums[], int n) 
	{ 
	    long prod[]=new long[n];
	    prod[0]=1L;
	    
        for(int i=1;i<n;i++){
            prod[i]=nums[i-1]*prod[i-1];
        }
        
        long R=1;
        for(int i=n-1;i>=0;i--){
            prod[i]*=R;
            R*=nums[i];
        }
        
        return prod;
	} 
} 

```
