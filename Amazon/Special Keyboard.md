```java

class Solution{
    static int optimalKeys(int n){
        if(n<=6) return n;
        
        int dp[]=new int[n+1];
        for(int i=1;i<=n;i++)   {
            if(i<=6){
                dp[i]=i;
            }else{
                for(int j=i-3;j>=1;j--){
                    int curr=dp[j]*(i-j-1);
                    dp[i]=Math.max(dp[i],curr);
                }
            }
        }
        
        return dp[n];
    }
}
```
