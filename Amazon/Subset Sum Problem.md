```java
class Solution{


    static Boolean isSubsetSum(int N, int arr[], int sum){
        Boolean dp[][]=new Boolean[N+1][sum+1];
        
        for(int i=0;i<=N;i++){
            for(int j=0;j<=sum;j++){
                if(j==0){
                    dp[i][j]=true;
                }else if(i==0){
                    dp[i][j]=false;
                }else{
                    dp[i][j]=j-arr[i-1]>=0 ? (dp[i-1][j] | dp[i-1][j-arr[i-1]]) : dp[i-1][j];
                }
            }
        }
        
        return dp[dp.length-1][dp[0].length-1];
    }
}
```
