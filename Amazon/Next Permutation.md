```java
class Solution{
    static List<Integer> nextPermutation(int N, int arr[]){
        List<Integer> ans=new ArrayList<>();
        for(int i: arr) ans.add(i);
        
        int i;
        for(i=N-2;i>=0;i--){
            if(ans.get(i)<ans.get(i+1)){
                break;
            }
        }
        
        if(i==-1)   {Collections.sort(ans); return ans;} 
        
        int j;
        for(j=N-1;j>i;j--){
            if(ans.get(j)>ans.get(i)){
                Collections.swap(ans,i,j);
                break;
            }
        }
        
        Collections.sort(ans.subList(i+1, N));
        
        return ans;
    }
}
```
