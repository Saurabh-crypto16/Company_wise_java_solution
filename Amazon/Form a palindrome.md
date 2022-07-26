```java
class Solution{
    static int countMin(String str)
    {
        int dp[][]=new int[str.length()][str.length()];
        
        //nujmber of insertions = string length - length of longest palindromic subsequence   
        for(int g=0;g<dp.length;g++){
            for(int i=0,j=g;j<dp.length;i++,j++){
                if(g==0){
                    dp[i][j]=1;
                }else{
                    if(str.charAt(i)==str.charAt(j)){
                        dp[i][j]=dp[i+1][j-1]+2;
                    }else{
                        dp[i][j]=Math.max(dp[i][j-1],dp[i+1][j]);
                    }
                }
            }
        }
        
        return str.length()-dp[0][dp[0].length-1];
    }
}
```
