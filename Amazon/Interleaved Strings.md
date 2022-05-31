```java
class Solution {
	public boolean isInterLeave(String a,String b,String c)
	{
        if(a.length()+b.length()!=c.length())   return false;
        
        return solve(a,b,c,0,0,new Boolean[a.length()+1][b.length()+1]);
	}
	public boolean solve(String a,String b,String c,int i,int j,Boolean dp[][]){
	    if(i==a.length() && j==b.length()){
	        return true;
	    }
	    
	    if(dp[i][j]!=null)  return dp[i][j];
	    
      //if both curr char of a and that of b match that of c then make both the calls
	    if(i<a.length() && a.charAt(i)==c.charAt(i+j)){
	        boolean f1=solve(a,b,c,i+1,j,dp);
	        dp[i][j]=f1;
	        if(f1)  return f1;
	    }
	    
	    if(j<b.length() && b.charAt(j)==c.charAt(i+j)){
	        boolean f1=solve(a,b,c,i,j+1,dp);
	        dp[i][j]=f1;
	        if(f1)  return f1;
	    }
	    
	    return dp[i][j]=false;
	}
}


```
