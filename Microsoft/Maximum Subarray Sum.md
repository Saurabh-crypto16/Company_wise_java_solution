```java
public class Solution {
	public static long maxSubarraySum(int[] arr, int n) {
		long c_sum=arr[0],o_sum=arr[0];
		
		for(int i=1;i<n;i++){
			if(c_sum<0){
				c_sum=(long)arr[i];
			}else{
				c_sum+=(long)arr[i];
			}
			
			o_sum=Math.max(o_sum,c_sum);
		}
		
		return o_sum < 0 ? 0 : o_sum;
	}

}
```
