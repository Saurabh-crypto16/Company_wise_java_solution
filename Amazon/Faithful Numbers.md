```java
class Solution {
    static Long nthFaithfulNum(int n) {
        long ans = 0;
        long base = 1;
        
        /*
        for each set bit in n compute 7^i
        eg: n=1=001=0*7^3+0*7^2+1*7^1
            n=5=101=1*7^3+0*7^2+1*7^1
        */
        
        while(n>0){
           int last = n&1;
           n = n>>1;
           
           ans += last*base;
           base = base*7;
        }
        
        return ans;
    }
};
```
