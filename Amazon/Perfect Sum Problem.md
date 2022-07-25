```java
class Solution{

	public int perfectSum(int arr[],int N, int sum) 
	{ 
	    int dp[][]=new int[N+1][sum+1],mod=(int)1e9+7;
        dp[0][0]=1;
        
        for(int i=1;i<=N;i++){
            for(int j=0;j<=sum;j++){
                if(j>=arr[i-1]){
                    dp[i][j]=((dp[i-1][j]%mod)+(dp[i-1][j-arr[i-1]]%mod))%mod;
                }else{
                    dp[i][j]=dp[i-1][j];
                }
            }
        }
        
        return dp[dp.length-1][dp[0].length-1]%mod;
	} 
}
```
