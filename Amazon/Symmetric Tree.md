```java
class GfG
{
    // return true/false denoting whether the tree is Symmetric or not
    public static boolean isSymmetric(Node root)
    {
        return check(root,root);
    }
    public static boolean check(Node root1,Node root2){
        if(root1==null || root2==null){
            return root1==null && root2==null;
        }
        
        return root1.data==root2.data && check(root1.left,root2.right) 
            && check(root1.right,root2.left);
    }
}
```
