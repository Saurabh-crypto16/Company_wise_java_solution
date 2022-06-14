```java
class Solution{
    int findNum(int n){
        int high=n*5,low=1,mid,ans=-1;
        
        while(low<=high){
            mid=low+((high-low)/2);
            if(numberOfTrailingZeros(mid)>=n){
               ans=mid;
               high=mid-1;
            }else{
               low=mid+1;
            }
        }
        
        return ans;
    }
    int numberOfTrailingZeros(int n){
        int ans=0,den=5;
        
        while((n/den)>0){
            ans+=(n/den);
            den*=5;
        }
        
        return ans;
    }
}
```
