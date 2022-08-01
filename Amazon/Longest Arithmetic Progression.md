```java

class Solution {
    int lengthOfLongestAP(int[] a, int n) {
        if(n<2) return n;
        HashMap<Integer,Integer> dp[]=new HashMap[n];
        int maxVal=1;
        
        for(int i=0;i<n;i++){
            int currVal=a[i];
            dp[i]=new HashMap<>();
            for(int j=0;j<i;j++){
                int diff=a[i]-a[j];
                int newVal=dp[j].getOrDefault(diff,0)+1;
                dp[i].put(diff,newVal);
                maxVal=Math.max(maxVal,newVal);
            }
        }
        
        return maxVal+1;
    }
}
```
