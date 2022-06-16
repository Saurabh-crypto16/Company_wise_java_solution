```java

class Solution
{
    static ArrayList<ArrayList<Integer>> res;
    //Function to return a list of indexes denoting the required 
    //combinations whose sum is equal to given number.
    static ArrayList<ArrayList<Integer>> combinationSum(ArrayList<Integer> A, int B)
    {
        res=new ArrayList<>();
        Set<Integer> set = new HashSet<>(A);
        A.clear();
        A.addAll(set);
        Collections.sort(A);
        solve(A,B,0,new ArrayList<Integer>());
        
        return res;
    }
    static void solve(ArrayList<Integer> A,int B,int start,ArrayList<Integer> list){
        if(B<0) return;
        
        if(B==0 && !res.contains(list)){
            res.add(new ArrayList(list));
            return;
        }
        
        for(int i=start;i<A.size();i++){
            list.add(A.get(i));
            solve(A,B-A.get(i),i,list);
            list.remove(list.size()-1);
        }
    }
}
```
