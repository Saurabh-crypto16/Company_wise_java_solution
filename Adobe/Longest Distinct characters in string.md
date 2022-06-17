```java
class Solution{
    static int longestSubstrDistinctChars(String S){
        HashMap<Character,Integer> map=new HashMap<>();
        int left=0,right=0,ans=0;
        
        while(right<S.length()){
            if(map.containsKey(S.charAt(right))){
                //System.out.println(S.charAt(right));
                left=Math.max(left,map.get(S.charAt(right))+1);
            }
            
            map.put(S.charAt(right),right);
            ans=Math.max(ans,right-left+1);
            right++;
        }
        
        return ans;
    }
}
```
