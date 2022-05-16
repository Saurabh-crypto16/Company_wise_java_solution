```java
class Solution{
    // Function for finding maximum and value pair
    public static int lenOfLongSubarr (int A[], int N, int k) {
        Map<Integer,Integer> map=new HashMap<>();
        int ans=0,sum=0;
        
        for(int i=0;i<N;i++){
            sum+=A[i];
            
            if(sum==k && ans==0)    ans++;
            if(sum==k)  ans=i+1;
            
            if(map.containsKey(sum-k)){
                ans=Math.max(ans,i-map.get(sum-k));
            }
            if(!map.containsKey(sum)){
                map.put(sum,i);
            }
        }
        
        return ans;
    }
}

```
