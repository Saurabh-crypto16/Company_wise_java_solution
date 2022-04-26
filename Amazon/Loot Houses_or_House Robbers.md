```java
import java.util.*;

public class Solution {
	public static int maxMoneyLooted(int[] houses) {
		if(houses==null || houses.length==0)	return 0;
		if(houses.length==1)	return houses[0];
		if(houses.length==2)	return Math.max(houses[0],houses[1]);
		
		int dp[]=new int[houses.length];
		dp[0]=houses[0];
		dp[1]=Math.max(houses[0],houses[1]);
		
		for(int i=2;i<houses.length;i++){
			dp[i]=Math.max(houses[i]+dp[i-2],dp[i-1]);
		}
		
		return dp[houses.length-1];
	}
}
```
