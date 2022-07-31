```java
class Solution
{
    public int nthPoint(int n)
    {
        int dp[]=new int[n+1],mod=(int)1e9+7;
        dp[0]=1;
        
        for(int i=1;i<=n;i++){
            if(i==1){
                dp[i]=dp[i-1];
            }else{
                dp[i]=(dp[i-1]+dp[i-2])%mod;
            }
        }
        
        return dp[n];
    }
}
```
