```java
Solution 1 - O(K*N*N) time
class Solution {
    static int maxProfit(int k, int n, int a[]) {
        if(n<2) return 0;
        int dp[][]=new int[k+1][n];
        
        for(int i=1;i<=k;i++){
            for(int j=1;j<n;j++){
                dp[i][j]=Math.max(dp[i][j-1],helper(i,j,a,dp));
            }
        }
        
        return dp[k][n-1];
    }
    public static int helper(int k,int x,int[] a,int[][] dp){
        int max=0;
        for(int j=0;j<x;j++){
            max=Math.max(max,a[x]-a[j]+dp[k-1][j]);
        }
        
        return max;
    }
}


Solution 2 - O(K*N) time
class Solution {
    static int maxProfit(int k, int n, int a[]) {
        if(n<2) return 0;
        int dp[][]=new int[k+1][n];
        
        for(int i=1;i<=k;i++){
            int effectiveBuyPrice=a[0];
            for(int j=1;j<n;j++){
                dp[i][j]=Math.max(dp[i][j-1],a[j]-effectiveBuyPrice);
                effectiveBuyPrice=Math.min(effectiveBuyPrice,a[j]-dp[i-1][j]);
            }
        }
        
        return dp[k][n-1];
    }
}
```
