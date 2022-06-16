```java

class Solution {
    int getMinDiff(int[] arr, int n, int k) {
        Arrays.sort(arr);
        
        int ans=arr[n-1]-arr[0];
        int smallest=arr[0]+k;
        int largest=arr[n-1]-k;
        int mi,ma;
        
        for(int i=0;i<n-1;i++){
            //in any sorted ans the min diff will be between adjacent elements 
            mi=Math.min(smallest,arr[i+1]-k);
            ma=Math.max(largest,arr[i]+k);
            
            if(mi<0)    continue;
            ans=Math.min(ans,ma-mi);
        }
        
        return ans;
    }
}

```
