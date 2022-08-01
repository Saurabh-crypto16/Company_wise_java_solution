```java

class Solution{
    int dp[][];
    public Boolean is1winner(int N, int arr[]){
        dp=new int[N+1][N+1];
        for(int d[]: dp)    Arrays.fill(d,-1);
        
        int sum=0;
        for(int i: arr) sum+=i;
        
        int player1=solve(0,N-1,arr);
        
        return player1 > (sum-player1);
    }
    public int solve(int i,int j,int[] arr){
        if(i>j) return 0;
        
        if(dp[i][j]!=-1)    return dp[i][j];
        
        int ans1=arr[i]+Math.min(solve(i+2,j,arr),solve(i+1,j-1,arr));
        int ans2=arr[j]+Math.min(solve(i,j-2,arr),solve(i+1,j-1,arr));
        
        return dp[i][j]=Math.max(ans1,ans2);
    }
}
```
