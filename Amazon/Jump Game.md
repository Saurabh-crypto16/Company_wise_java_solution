```java
class Solution {
    static int canReach(int[] A, int n) {
        int lastGoodIdx=n-1;
        
        for(int i=n-1;i>=0;i--){
            if(i+A[i]>=lastGoodIdx){
                lastGoodIdx=i;
            }
        }
        
        return lastGoodIdx==0 ? 1 : 0;
    }
};
```
