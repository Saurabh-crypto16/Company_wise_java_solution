```java
class Solution{
    static class MaxNode{
        int max;
        int min;
        int size;
        MaxNode(int min,int max,int size){
            this.min= min;
            this.max=max;
            this.size=size;
        }
    }
    // Return the size of the largest sub-tree which is also a BST
    static int largestBst(Node root){
        return  largestBstUtil(root).size;
    }
    public static MaxNode largestBstUtil(Node root){
        if(root==null)  return new MaxNode(Integer.MAX_VALUE,Integer.MIN_VALUE,0);
        
        MaxNode left=largestBstUtil(root.left);
        MaxNode right=largestBstUtil(root.right);
        
        //valid BST if root > max of left subtree as left subtree has val less than root
        //and root < min of right subtree
        if(root.data>left.max && root.data<right.min){
            return new MaxNode(Math.min(root.data,left.min),Math.max(root.data,right.max),
                left.size+right.size+1);
        }
        
        //Not valid BST
        return new MaxNode(Integer.MIN_VALUE,Integer.MAX_VALUE,Math.max(left.size,right.size));
    }
}
```
