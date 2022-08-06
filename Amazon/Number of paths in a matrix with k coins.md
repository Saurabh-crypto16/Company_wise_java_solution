```java
class Solution {
    long dp[][][];
    long numberOfPath(int n, int K, int [][]arr) {
        dp = new long[n][n][K+1];
        for(int i=0;i<n;i++)
            for(int j=0;j<n;j++)
                for(int l=0;l<=K;l++)
                  dp[i][j][l]=-1;
                
        return solve(0,0,K,0,arr);
    }
    public long solve(int i,int j,int k,int sum,int[][] arr){
        if(i<0 || i>=arr.length || j<0 || j>=arr[0].length || sum+arr[i][j]>k){
            return 0L;
        }
        
        if(i==arr.length-1 && j==arr[0].length-1 && sum+arr[i][j]==k){
            return 1L;
        }
        
        if(dp[i][j][sum] != -1) 
            return dp[i][j][sum];
        
        return dp[i][j][sum]=solve(i+1,j,k,sum+arr[i][j],arr)+solve(i,j+1,k,sum+arr[i][j],arr);
    }
}
```
