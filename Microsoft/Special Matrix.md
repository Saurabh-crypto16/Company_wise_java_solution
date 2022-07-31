```java
class Solution
{
    public int FindWays(int n, int m, int[][] blocked_cells)
    {
        int dp[][]=new int[n][m],mod=(int)1e9+7;
        
        for(int[] b: blocked_cells){
            dp[b[0]-1][b[1]-1]=-1;    
        }
        
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(dp[i][j]==-1){
                    continue;
                }else if(i==0 && j==0){
                    dp[i][j]=1;
                }else if(j==0 && dp[i-1][j]!=-1){
                    dp[i][j]=dp[i-1][j];
                }else if(i==0 && dp[i][j-1]!=-1){
                    dp[i][j]=dp[i][j-1];
                }else if(i>0 && j>0){
                    if(dp[i-1][j]!=-1 && dp[i][j-1]!=-1){
                        dp[i][j]=(dp[i-1][j]+dp[i][j-1])%mod;
                    }else if(dp[i-1][j]!=-1){
                        dp[i][j]=dp[i-1][j];
                    }else{
                        dp[i][j]=dp[i][j-1];
                    }
                }
            }
        }
        
        return dp[n-1][m-1]<0 ? 0 : dp[n-1][m-1];
    }
}
```
