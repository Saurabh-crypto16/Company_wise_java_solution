```java
class Solution
{
    //Function to count the number of ways in which frog can reach the top.
    static long countWays(int n)
    {
        int dp[]=new int[n+1];
        dp[0]=1;
        int mod=(int)1e9+7;
        
        for(int i=1;i<=n;i++){
            if(i==1){
                dp[i]=dp[i-1];
            }else if(i==2){
                dp[i]=(dp[i-1]+dp[i-2])%mod;
            }else{
                dp[i]=((dp[i-1]+dp[i-2])%mod+(dp[i-3])%mod)%mod;
            }
        }
        
        return dp[n];
    }
    
}


```
