```java
//approach is to add the largest length rope as less as possible and smallest length rope as more as possible
import java.util.*;
public class Solution {
    public static long connectRopes(int[] arr){
        PriorityQueue<Integer> pq=new PriorityQueue<>();
		int cost=0;
		
		for(int a: arr)	pq.offer(a);
		
		while(pq.size()>1){
			int curr_cost=pq.poll()+pq.poll();
			cost+=curr_cost;
			pq.offer(curr_cost);
		}
		
		return cost;
    }
}
```
