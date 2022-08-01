```java
class Solution
{
    public int CountPS(String s, int n)
    {
        boolean dp[][]=new boolean[n][n];
        int cnt=0;
        
        for(int g=0;g<dp.length;g++){
            for(int i=0,j=g;j<dp[0].length;i++,j++){
                if(g==0){
                    dp[i][j]=true;
                }else if(g==1){
                    dp[i][j]=s.charAt(i)==s.charAt(j);
                }else{
                    if(s.charAt(i)==s.charAt(j) && dp[i+1][j-1]){
                        dp[i][j]=true;
                    }else{
                        dp[i][j]=false;
                    }
                }
                if(dp[i][j])    cnt++;
            }
        }
        
        return cnt-n;
    }
}
```
