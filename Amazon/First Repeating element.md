```java
class Solution {
    // Function to return the position of the first repeating element.
    public static int firstRepeated(int[] arr, int n) {
        HashMap<Integer,Integer> map=new HashMap<>();
        
        int idx=Integer.MAX_VALUE;
        for(int i=0;i<n;i++){
            if(map.containsKey(arr[i]) && map.get(arr[i])<idx){
                idx=map.get(arr[i]);
            }else{
                map.put(arr[i],i);
            }
        }
        
        return idx==Integer.MAX_VALUE ? -1 : idx+1;
    }
}

```
