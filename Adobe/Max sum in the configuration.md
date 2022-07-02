```java
class GfG
{
    int max_sum(int a[], int n)
    {
	    int sum=0,si=0;
	    for(int i=0;i<n;i++){
	        sum+=a[i];
	        si+=(i*a[i]);
	    }
	    
	    //Si+1=Si+sum-n*arr[n-i-1]
	    int max=si;
	    for(int i=0;i<n-1;i++){
	        int siplus1=si+sum-(n*a[n-1-i]);
	        
	        max=Math.max(max,siplus1);
	        si=siplus1;
	    }
	    
	    return max;
    }	
}
```
