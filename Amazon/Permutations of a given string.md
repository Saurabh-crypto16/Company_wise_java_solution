```java
class Solution {
    List<String> res;
    public List<String> find_permutation(String S) {
        res=new ArrayList<String>();
        
        solve(S.length(),S,"");
        Collections.sort(res);
        return res;
    }
    public void solve(int n,String s,String curr){
        if(curr.length()==n){
            if(!res.contains(curr))
                res.add(curr);
            return;
        }
        
        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            String before=s.substring(0,i);
            String after=s.substring(i+1);
            solve(n,before+after,curr+ch);
        }
    }
}
```
