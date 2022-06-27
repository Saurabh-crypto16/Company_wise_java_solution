```java
class Solution {
    long maxProduct(int[] arr, int n) {
        if(n<3) return -1;
        
        long min1=Long.MAX_VALUE,min2=Long.MAX_VALUE;
        long max1=Long.MIN_VALUE,max2=Long.MIN_VALUE,max3=Long.MIN_VALUE;
        
        for(int num: arr){
            if(num>=max1){
                max3=max2;
                max2=max1;
                max1=num;
            }else if(num>=max2){
                max3=max2;
                max2=num;
            }else if(num>=max3){
                max3=num;
            }
            
            if(num<=min1){
                min2=min1;
                min1=num;
            }else if(num<=min2){
                min2=num;
            }
        }
        
        return Math.max(min1*min2*max1,max1*max2*max3);
    }
}

```
