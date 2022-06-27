```java
class Solve{
    
    long maxArea(int A[], int len){
        int i=0,j=len-1;
        int ans=0;
        
        while(i<j){
            if(A[i]<A[j]){
                ans=Math.max(ans,A[i]*(j-i));
                i++;
            }else{
                ans=Math.max(ans,A[j]*(j-i));
                j--;
            }
        }
        
        return ans;
    }
}
```
