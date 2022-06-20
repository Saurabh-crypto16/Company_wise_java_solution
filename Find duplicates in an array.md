```java
class Solution {
    public static ArrayList<Integer> duplicates(int arr[], int n) {
        TreeSet<Integer> ans=new TreeSet<Integer>();
        Set<Integer> set=new HashSet<>();
        
        for(int i: arr){
            if(set.contains(i) && !ans.contains(i)){
                ans.add(i);
            }
            set.add(i);
        }
        
        if(ans.isEmpty())   ans.add(-1);
        
        
        return new ArrayList<Integer>(ans);
    }
}

```
