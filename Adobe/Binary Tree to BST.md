```java
class Solution
{
    int idx=0;
    public void findInorder(Node root,ArrayList<Integer> inorder){
        if(root==null)  return;
        
        findInorder(root.left,inorder);
        inorder.add(root.data);
        findInorder(root.right,inorder);
    }
    public void replaceByInorder(Node root,ArrayList<Integer> inorder){
        if(root==null)  return;
        
        replaceByInorder(root.left,inorder);
        root.data=inorder.get(idx++);
        replaceByInorder(root.right,inorder);
    }
    // The given root is the root of the Binary Tree
    // Return the root of the generated BST
    Node binaryTreeToBST(Node root){
       ArrayList<Integer> inorder=new ArrayList<>();
       findInorder(root,inorder);
       Collections.sort(inorder);
       
       replaceByInorder(root,inorder);
       
       return root;
    }
}
 
 ```
