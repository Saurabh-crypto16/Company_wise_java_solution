```java
class Solution{
    static long arrangeTiles(int n){
        long dp[]=new long[n+1];
        
        //dp[i]=dp[i-4]+dp[i-1]
        
        for(int i=0;i<=n;i++){
            if(i<4){
                dp[i]=1;
            }else {
                dp[i]=(dp[i-1]+dp[i-4]);
            }
        }
        
        return dp[n];
    }
}
```
