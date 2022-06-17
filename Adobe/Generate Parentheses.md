```java
class Solution {
    List<String> res;
    public List<String> AllParenthesis(int n) 
    {
        res=new ArrayList<>();
        solve("",n,n);
        
        return res;
    }
    public void solve(String curr,int open,int close){
        if(open==0 && close==0){
            res.add(curr);
            return;
        }
        
        if(open>0){
            solve(curr+"(",open-1,close);
        }
        if(close>0 && open<close){
            solve(curr+")",open,close-1);
        }
    }
}
```
