```java
class Solution
{
    int dp[][],mod=(int)1e9+7;
    int  subsequenceCount(String s, String t)
    {
        dp=new int[s.length()][t.length()];
        for(int[] i: dp)    Arrays.fill(i,-1);
	    
	    return solve(0,s.length(),s,0,t.length(),t);
    }
    int solve(int i,int n,String s,int j,int m,String t){
        if(j==m)    return 1;
        if(i==n)    return 0;
        
        if(dp[i][j]!=-1)    return dp[i][j]%mod;
        
        if(s.charAt(i)==t.charAt(j))  
            //when chars are matching there are two options either to match the curr char or 
            //move forward without matching
            return dp[i][j]=(solve(i+1,n,s,j+1,m,t)%mod+solve(i+1,n,s,j,m,t)%mod)%mod;
        else
            return dp[i][j]=solve(i+1,n,s,j,m,t)%mod;
    }
}
```
