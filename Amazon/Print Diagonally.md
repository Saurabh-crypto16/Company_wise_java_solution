```java
class Solution{
    static ArrayList<Integer> downwardDigonal(int n, int A[][])
    {
        // code here 
        TreeMap<Integer,ArrayList<Integer>> map=new TreeMap<>();
        
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                if(!map.containsKey(i+j))   map.put(i+j,new ArrayList<Integer>());
                map.get(i+j).add(A[i][j]);
            }
        }
        
        ArrayList<Integer> ans=new ArrayList<>();
        for(int key: map.keySet()){
            ans.addAll(map.get(key));
        }
        
        return ans;
    }
}

```
