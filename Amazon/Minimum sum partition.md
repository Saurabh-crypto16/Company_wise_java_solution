```java
class Solution
{

	public int minDifference(int arr[], int N) 
	{ 
	    //max possible sum using array elements
	    int sum=0;
	    for(int i: arr) sum+=i;
	    
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
        
        //last row contains if given sum can be formed using all elements
        int ans=sum;
        for(int j=0;j<=sum;j++){
            if(dp[dp.length-1][j]){
                ans=Math.min(ans,Math.abs(sum-2*j));
            }
        }
        
        return ans;
	} 
}
```
