```java
class Solution {
	boolean isPalin(String str){
	   int i = 0, j = str.length() - 1;
	   while (i < j) {	 
	   if (str.charAt(i++) != str.charAt(j--))
	       return false;
	            //i++;
	            //j--;
	   }
	        
	   return true;
    }
	
   ArrayList<ArrayList<String>> ans=new ArrayList<>();
   void solve(String str,String psf) {
    	if(str.length()==0) {
    		ArrayList<String> temp=new ArrayList<>();
    		String trash[]=psf.split(" ");
    		for(int i=1;i<trash.length;i++) {
    			temp.add(trash[i]);
    		}
    		
    		ans.add(temp);
    		return;
    	}
    	
		
		for(int i=0;i<str.length();i++) {
			String prefix=str.substring(0,i+1);
			String rest=str.substring(i+1);
			if(isPalin(prefix)==true) {
				solve(rest,psf+" "+prefix);
			}
		}
    }
    
    ArrayList<ArrayList<String>> allPalindromicPerms(String S) {
        solve(S,"");
        
        return ans;
    }
};
```
