```java
public class Solution {
    public static long getMaximumProfit (int n, long[] values) {
        long ans=0;
		
		for(int i=1;i<values.length;i++){
			if(values[i]>values[i-1]){
				ans+=(values[i]-values[i-1]);
			}
		}
		
		return ans;
    }
}
```
