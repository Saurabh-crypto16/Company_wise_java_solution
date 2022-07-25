```java
class Solution{
    static int palindromicPartition(String str)
    {
        boolean dp[][]=new boolean[str.length()][str.length()];
        
        for(int g=0;g<str.length();g++){
            for(int i=0,j=g;j<dp.length;i++,j++){
                if(g==0){
                    dp[i][j]=true;
                }else if(g==1){
                    dp[i][j]=str.charAt(i)==str.charAt(j);
                }else if(str.charAt(i)==str.charAt(j) && dp[i+1][j-1]){
                    dp[i][j]=true;
                }
            }
        }
        
        int strg[]=new int[str.length()];
        
        for(int j=1;j<strg.length;j++){
            if(dp[0][j]){
                strg[j]=0;
            }else{
                int min=Integer.MAX_VALUE;
                for(int i=j;i>=1;i--){
                    if(dp[i][j] && strg[i-1]<min){
                        min=strg[i-1];
                    }
                }
                strg[j]=min+1;
            }
        }
        
        return strg[strg.length-1];
    }
}
```
