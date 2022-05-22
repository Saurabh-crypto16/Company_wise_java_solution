```java
class Solution{
    public static void flatten(Node root){
        if(root==null)  return;
        
        if(root.left!=null){
            flatten(root.left);
            
            Node temp=root.right;
            root.right=root.left;
            root.left=null;
            
            Node curr=root.right;
            while(curr.right!=null){
                curr=curr.right;
            }
            
            curr.right=temp;
        }
        
        flatten(root.right);
    }
}
```
