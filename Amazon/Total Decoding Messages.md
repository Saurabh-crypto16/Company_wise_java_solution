```java
class Solution
{
    public int CountWays(String str)
    {
        int dp[]=new int[str.length()+1],mod=(int)1e9+7;
        
        dp[0]=1;
        dp[1]=str.charAt(0)=='0' ? 0 : 1;
        
        for(int i=2;i<=str.length();i++){
            int oneDigit=Integer.parseInt(str.substring(i-1,i));
            int twoDigit=Integer.parseInt(str.substring(i-2,i));
            
            if(oneDigit>0)  dp[i]=(dp[i]%mod+dp[i-1]%mod)%mod;
            if(twoDigit>=10 && twoDigit<=26)  dp[i]=(dp[i]%mod+dp[i-2]%mod)%mod;
        }
        
        return dp[dp.length-1];
    }
}
```
