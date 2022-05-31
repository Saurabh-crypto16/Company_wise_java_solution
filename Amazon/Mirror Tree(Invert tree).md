```java
class Solution {
    // Function to convert a binary tree into its mirror tree.
    void mirror(Node node) {
        if(node==null)  return;
        
        node=invert(node);
    }
    public Node invert(Node node){
        if(node==null)  return node;
        
        Node left=invert(node.left);
        Node right=invert(node.right);
        
        node.left=right;
        node.right=left;
        
        return node;
    }
}
```
