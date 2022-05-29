```java
class Tree{
	static void reverseAlternate( Node root){  
       preorder(root.left,root.right,0);
    }  
    public static void preorder(Node root1,Node root2,int level){
        if(root1==null || root2==null)  return;
        
        if(level%2==0){
            int temp=root1.data;
            root1.data=root2.data;
            root2.data=temp;
        }
        
        preorder(root1.left,root2.right,level+1);
        preorder(root1.right,root2.left,level+1);
    }
}
```
