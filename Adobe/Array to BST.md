```java
class Solution
{
    int i=0;
    public int[] sortedArrayToBST(int[] nums)
    {
        int arr[]=new int[nums.length];
        solve(arr,nums,0,nums.length-1);
        
        return arr;
    }
    public void solve(int arr[],int nums[],int left,int right){
        if(left>right)  return;
        
        int mid=left+(right-left)/2;
        arr[i++]=nums[mid];
        solve(arr,nums,left,mid-1);
        solve(arr,nums,mid+1,right);
    }
}
```
