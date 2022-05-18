```java
class Solution {
    static int dp[][];
    static int eggDrop(int e, int k) {
	    dp=new int[e+1][k+1];
	    for(int d[]: dp)    Arrays.fill(d,-1);
	    
	    return eggDropUtil(e,k);
	}
	public static int eggDropUtil(int e,int k){
	    if(k==0 || k==1)    return k;
	    if(e==1)    return k;
	    if(dp[e][k]!=-1)    return dp[e][k];
	    
	    int min=Integer.MAX_VALUE;
	    for(int f=1;f<=k;f++){
          //eggDropUtil(e,k-f) means if egg did not break at f floor then critical floor should be above f so k-f
          //eggDropUtil(e-1,f-1) means if egg breaks at f floor then critical floor should be below f so f-1
          //we take max value of both because we consider our luck to me worst
	        int cost=1+Math.max(eggDropUtil(e,k-f),eggDropUtil(e-1,f-1));
	        min=Math.min(min,cost);
	    }
	    
	    return dp[e][k]=min;
	}
}
```
