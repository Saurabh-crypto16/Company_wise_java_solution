```java
class Solution {
    public static int maxProfit(int n, int[] price) {
        int c1=Integer.MAX_VALUE,c2=Integer.MAX_VALUE;
        int p1=0,p2=0;
        
        for(int i=0;i<n;i++){
            c1=Math.min(c1,price[i]);
            p1=Math.max(p1,price[i]-c1);
            c2=Math.min(c2,price[i]-p1);
            p2=Math.max(p2,price[i]-c2);
        }
        
        return p2;
    }
}
        

```
