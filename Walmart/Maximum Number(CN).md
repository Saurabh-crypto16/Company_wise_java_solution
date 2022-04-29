```java
import java.util.*;

public class Solution {

	public static ArrayList<Integer> maxSwap(ArrayList<Integer> num, int N) {
		int digits[]=new int[10];
		for(int n: num)	digits[n]++;
		
		//checking if digits are in decreasing order or not
		//if not replace it with the largest digit between that idx and num.size()-1
		int start=0;
		for(int i=digits.length-1;i>=0;i--){
			while(digits[i]>0){
				if(num.get(start)==i){
					start++;
					digits[i]--;
				}else{
					for(int j=num.size()-1;j>start;j--){
						if(num.get(j)==i){
							Collections.swap(num,start,j);
							return num;
						}
					}
				}
			}
		}
		
		return num;
	}
}
```
