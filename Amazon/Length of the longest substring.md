```java
class Solution{
    int longestUniqueSubsttr(String S){
        HashMap<Character,Integer> map=new HashMap<>();
        int ans=0,left=0,right=0;
        
        while(right<S.length()){
            if(map.containsKey(S.charAt(right))){
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
