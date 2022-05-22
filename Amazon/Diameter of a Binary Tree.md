```java
class Solution {
    // Function to return the diameter of a Binary Tree.
    int ans=0;
    int diameter(Node root) {
        if(root==null){
            return ans;
        }
        
        ans=Math.max(ans,height(root.left)+height(root.right)+1);
        
        return Math.max(ans,Math.max(diameter(root.left),diameter(root.right)));
    }
    int height(Node root){
        if(root==null)  return 0;
        
        return 1+Math.max(height(root.left),height(root.right));
    }
}
```
