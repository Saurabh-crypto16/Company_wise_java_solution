```java
class Solution{
    int sum=0;
    public Node modify(Node root){
        solve(root);
        return root;
    }
    public void solve(Node root){
        if(root==null)  return;
        
        solve(root.right);
        sum+=root.data;
        root.data=sum;
        solve(root.left);
    }
}

```
