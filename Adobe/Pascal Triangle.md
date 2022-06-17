```java
class Solution {
    ArrayList<Long> nthRowOfPascalTriangle(int n) {
        ArrayList<Long> curr=new ArrayList<>();
        ArrayList<Long> prev=new ArrayList<>();
        prev.add(1L);
        long mod=(long)1e9+7;
        
        while(n-->1){
            for(int i=0;i<prev.size()-1;i++){
                curr.add((prev.get(i)%mod+prev.get(i+1)%mod)%mod);
            }
            
            curr.add(0,1L);
            curr.add(1L);
            
            prev=new ArrayList(curr);
            curr.clear();
        }
        
        return prev;
    }
}
```
