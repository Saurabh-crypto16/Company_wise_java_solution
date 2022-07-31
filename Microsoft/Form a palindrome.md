```java
class Solution{
    int findMinInsertions(String s){
        int dp[][]=new int[s.length()][s.length()];
        
        for(int g=0;g<dp.length;g++){
            for(int i=0,j=g;j<dp.length;i++,j++){
                if(g==0){
                    dp[i][j]=1;
                }else{
                    if(s.charAt(i)==s.charAt(j)){
                        dp[i][j]=dp[i+1][j-1]+2;
                    }else{
                        dp[i][j]=Math.max(dp[i+1][j],dp[i][j-1]);
                    }
                }
            }
        }
        
        return s.length()-dp[0][dp[0].length-1];
    }
}
```
