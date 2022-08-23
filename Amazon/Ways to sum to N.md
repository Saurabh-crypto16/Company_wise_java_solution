```java
class Solution
{
    public int countWays(int arr[], int m, int N) 
    { 
        int dp[]=new int[N+1];
        int mod=(int)1e9+7;
        
        dp[0]=1;
        for(int i=1;i<=N;i++){
            //System.out.println("for i="+i);
            for(int j=0;j<m;j++){
                if(i>=arr[j]){
                    //System.out.println(arr[j]);
                    dp[i]=(dp[i]+dp[i-arr[j]])%mod;
                }
            }
        }
         
         return dp[N];
    } 
}
```
