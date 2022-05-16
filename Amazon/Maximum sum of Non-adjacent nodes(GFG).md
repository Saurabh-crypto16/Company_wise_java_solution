```java
/*
arr[0] = max sum including node at that level
arr[1] = max sum excluding node at that level
*/
class Solution{
    //Function to return the maximum sum of non-adjacent nodes.
    static int getMaxSum(Node root){
        int ans[]=getMaxSumUtil(root);
        return Math.max(ans[0],ans[1]);
    }
    public static int[] getMaxSumUtil(Node root){
        if(root==null){
            return new int[]{0,0};
        }
        
        int left[]=getMaxSumUtil(root.left);
        int right[]=getMaxSumUtil(root.right);
        
        int arr[]=new int[2];
        arr[0]=root.data+left[1]+right[1];  //node included
        arr[1]=Math.max(left[0],left[1])+Math.max(right[0],right[1]);   //excluded
        
        return arr;
    }
}

```
