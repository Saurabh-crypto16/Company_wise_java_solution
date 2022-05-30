```java
class Solution {
    int kadanes(int arr[]){
        int currSum=arr[0],maxSum=arr[0];
        
        for(int i=1;i<arr.length;i++){
            currSum=Math.max(arr[i],currSum+arr[i]);
            maxSum=Math.max(maxSum,currSum);
        }
        
        return maxSum;
    }
    int maximumSumRectangle(int R, int C, int M[][]) {
        int ans=Integer.MIN_VALUE;
        
        //adding rows column wise to make an array and find max sum subarray from that
        //add rows from i=0 to i=r-1 and for each iteration find max sum
        //add rows from i=1 to i=r-1 and so on
        for(int i=0;i<R;i++){
            int currRow[]=new int[C];
            for(int j=i;j<R;j++){
                for(int k=0;k<C;k++){
                    currRow[k]+=M[j][k];
                }
                ans=Math.max(ans,kadanes(currRow));
            }
        }
        
        return ans;
    }
}
```
